<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Built for Any Screen",
    description:
        "Your website looks great everywhere — from laptops in cafés to phones on the trail. I test and optimize on real devices, in real settings.",
  },
  {
    icon: "badgeCheck",
    title: "Trust Built-In",
    description:
        "Designs that inspire confidence and connection. Authenticity comes first — no generic templates, just real work for real people.",
  },
  {
    icon: "goal",
    title: "Focused Messaging",
    description:
        "Every word and pixel serves your goals. Whether you're building a brand or sharing a passion, I keep your message sharp and on point.",
  },
  {
    icon: "pictureInPicture",
    title: "Eye-Catching Visuals",
    description:
        "Crafted with clean layouts and immersive visuals that reflect your vibe — whether you're city-based or mountain-minded.",
  },
  {
    icon: "mousePointerClick",
    title: "Action-Driven Design",
    description:
        "Clear buttons. Easy paths. No fluff. Each site is built to guide your visitors exactly where you want them to go.",
  },
  {
    icon: "newspaper",
    title: "Headline that Hits",
    description:
        "I craft bold, simple headlines that grab attention — inspired by your story and shaped by what matters most.",
  },
];


const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      My Approach
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      What Sets My Work Apart
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      I design and build websites where ideas flow — whether it’s on a mountain trail, in a city park, or from a quiet cabin. Real-life testing, real connection, and real results.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
