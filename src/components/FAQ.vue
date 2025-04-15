<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question: "How long will it take to build my website?",
    answer:
        "Most small to medium websites are completed within 1–3 weeks depending on the complexity, features, and how quickly you provide content and feedback.",
    value: "item-1",
  },
  {
    question: "Will my website be mobile-friendly?",
    answer:
        "Absolutely. Every site I build is fully responsive and tested across all major screen sizes to ensure it looks great and works perfectly on mobile, tablet, and desktop.",
    value: "item-2",
  },
  {
    question: "Can I update the website content myself later?",
    answer:
        "Yes, I typically use content management systems like WordPress or build custom dashboards so you can easily update text, images, and blog posts on your own.",
    value: "item-3",
  },
  {
    question: "Do you offer website maintenance after launch?",
    answer:
        "Yes! I offer ongoing maintenance plans that include updates, backups, security checks, and performance monitoring to keep your site running smoothly.",
    value: "item-4",
  },
  {
    question: "Can you help with SEO and loading speed?",
    answer:
        "Definitely. I follow modern SEO practices and optimize every page for fast loading times by minimizing code, compressing images, and using best practices.",
    value: "item-5",
  },
];
</script>

<template>
  <section
    id="faq"
    class="container md:w-[700px] py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQS</h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Common Questions
      </h2>
    </div>

    <Accordion
      type="single"
      collapsible
      class="AccordionRoot"
    >
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left"> {{ question }} </AccordionTrigger>

        <AccordionContent>{{ answer }}</AccordionContent>
      </AccordionItem>
    </Accordion>
  </section>
</template>
