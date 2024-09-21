<template>
  <div class="max-w-6xl mx-auto py-12">
    <h2 class="my-12 text-[40px] leading-[26px] font-semibold">FAQs</h2>
    <div class="grid grid-cols-2 gap-6">
      <div class="space-y-4">
        <div
          v-for="(faq, index) in faqs.slice(0, 3)"
          :key="index"
          :class="[
            'border rounded-lg p-4 bg-white',
            faq.isOpen ? 'border-[#459D7A]' : 'border-[#DEE1E6]',
          ]"
        >
          <button
            class="flex justify-between w-full text-lg font-semibold"
            :class="faq.isOpen ? 'text-green-700' : 'text-gray-700'"
            @click="toggleFAQ(index)"
          >
            {{ faq.question }}
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                v-if="faq.isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M9 19l7-7-7-7"
              />
            </svg>
          </button>
          <p v-if="faq.isOpen" class="mt-2 text-gray-500">
            {{ faq.answer }}
          </p>
        </div>
      </div>

      <div class="space-y-4">
        <div
          v-for="(faq, index) in faqs.slice(3, 8)"
          :key="index"
          :class="[
            'border rounded-lg p-4 bg-white',
            faq.isOpen ? 'border-[#459D7A]' : 'border-[#DEE1E6]',
          ]"
        >
          <button
            class="flex justify-between w-full text-lg font-semibold"
            :class="faq.isOpen ? 'text-[#459D7A]' : 'text-gray-700'"
            @click="toggleFAQ(index + 3)"
          >
            {{ faq.question }}
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                v-if="faq.isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M9 19l7-7-7-7"
              />
            </svg>
          </button>
          <p v-if="faq.isOpen" class="mt-2 text-gray-500">
            {{ faq.answer }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
interface iFAQ {
  question: string;
  answer: string;
  isOpen: boolean;
}

const faqs = ref<iFAQ[]>([
  {
    question: "Nisi nisi magna nostrud non consequat conse?",
    answer:
      "Ullamco enim ut culpa irure non qui est duis et aute proident reprehenderit tempor mollit.",
    isOpen: true,
  },
  {
    question:
      "Nostrud eiusmod exercitation duis reprehenderit laboris ullamco. Magna culpa cillum?",
    answer:
      "Aliquip excepteur nisi culpa reprehenderit adipiscing aliquip excepteur nulla minim.",
    isOpen: false,
  },
  {
    question: "Fugiat pariatur minim eiusmod aute adipisicing aliqua occaecat?",
    answer:
      "Excepteur nulla sint sunt laboris reprehenderit occaecat mollit velit.",
    isOpen: false,
  },
  {
    question: "How do I reset my password?",
    answer:
      "You can reset your password by clicking on 'Forgot Password' at the login page.",
    isOpen: false,
  },
  {
    question: "Can I cancel my subscription?",
    answer:
      "Yes, you can cancel your subscription at any time from your account settings page.",
    isOpen: false,
  },
  {
    question: "What is your refund policy?",
    answer: "We offer a 30-day money-back guarantee on all plans.",
    isOpen: false,
  },
  {
    question: "How do I contact support?",
    answer: "You can contact support through email or our 24/7 live chat.",
    isOpen: false,
  },
]);

const toggleFAQ = (index: number) => {
  faqs.value.forEach((faq, i) => {
    faq.isOpen = i === index ? !faq.isOpen : false;
  });
};
</script>
