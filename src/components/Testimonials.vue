<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://github.com/shadcn.png",
    name: "John Doe",
    userName: "Startup Founder",
    comment:
        "Absolutely amazing experience! The website was delivered on time, looked stunning, and worked flawlessly on all devices. Highly recommended.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Sophia Collins",
    userName: "Digital Marketing Specialist",
    comment:
        "Clear communication, modern design, and SEO-friendly structure — this developer gets everything right. Will definitely hire again.",
    rating: 4.8,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Adam Johnson",
    userName: "E-commerce Manager",
    comment:
        "Our online store now loads twice as fast and looks 10x better. The custom features were exactly what we needed. Excellent work.",
    rating: 4.9,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Ethan Parker",
    userName: "Creative Director",
    comment:
        "Delivered pixel-perfect results based on our Figma designs. Even added useful suggestions that improved the final product.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Ava Mitchell",
    userName: "Small Business Owner",
    comment:
        "I finally have a site I’m proud to show clients. Easy to update, loads fast, and works perfectly on phones. Super happy with the results.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Isabella Reed",
    userName: "Product Manager",
    comment:
        "Professional, responsive, and skilled. Took our brief and turned it into something way beyond what we imagined. 10/10.",
    rating: 4.9,
  },
];

</script>

<template>
  <section
    id="testimonials"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Testimonials
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Hear What Our 1000+ Clients Say
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              "{{ review.comment }}"
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage
                    src="https://www.radix-vue.com/logo.svg"
                    alt="@radix-vue"
                  />
                  <AvatarFallback>SV</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
