<script setup lang="ts">
import {Card, CardContent, CardHeader, CardTitle} from "@/components/ui/card";
import {Badge} from "@/components/ui/badge";

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: "Crypto",
    title: "Crypto Exchange Web Platform",
    description:
        "Designed and built a modern, mobile-friendly website for fast and secure cryptocurrency exchanges. Integrated third-party APIs and real-time updates.",
    image: "crypto.png",
  },
  {
    badgeTitle: "Telegram Bot",
    title: "Smart Bot System for Businesses",
    description:
        "Developed a web interface and backend to manage a highly customizable Telegram bot for a company. Features include message automation, customer support, and analytics.",
    image: "tgph.png",
  },
  {
    badgeTitle: "Travel",
    title: "Flight Booking Web App",
    description:
        "Created a user-friendly interface for a plane ticket booking system with multiple payment options and dynamic search capabilities.",
    image: "bilets.png",
  },
  {
    badgeTitle: "Infrastructure",
    title: "Smart Maintenance Control System",
    description:
        "Built the frontend and backend for a system monitoring service quality in city-level electrical switchboards. Included alerting, analytics, and role-based access.",
    image: "control_system.png",
  },
];

</script>

<template>
  <section
      id="features"
      class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        My Projects
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Selected Work in Action
      </h2>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="(
          { badgeTitle, title, description, image }, index
        ) in HowItWorksList"
        :key="title"
        :class="[
          'flex flex-col mb-8 items-center md:flex-row lg:flex-row',
          index % 2 !== 0 ? 'md:flex-row-reverse lg:flex-row-reverse' : ''
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge>{{ badgeTitle }}</Badge>
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>

        <img
            :src="image"
            :alt="`Image describing ${title} `"
            class="w-[300px] md:w-[400px] lg:w-[600px] mx-auto"
        />

        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>

  </section>
</template>
