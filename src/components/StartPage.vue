<template>
  <v-container>
    <v-card
        class="mt-4"
    >
      <v-row class="text-center">
        <v-row class="mt-4" justify="space-around">
          <v-avatar
              class="elevation-3"
              size="150px"
          >
            <img
                :src="require('@/assets/avatar.jpg')"
            >
          </v-avatar>
        </v-row>
      </v-row>
      <v-row class="text-center">
        <v-col class="mb-4">
          <h1 class="display-2 font-weight-bold mb-3">
            Меренков Николай
          </h1>

          <p class="subheading font-weight-regular">
            Мастер по ремонту ноутбуков и ПК.
          </p>
        </v-col>
      </v-row>
      <v-row class="text-center" justify="space-around">
        <v-col
            class="mb-5"
            cols="10"
            lg="8"
            md="10"
            sm="10"
            xs="10"

        >
          <v-row justify="center">
            <v-expansion-panels popout>
              <v-expansion-panel
                  v-for="(message, i) in messages"
                  :key="i"
                  hide-actions
                  class="mb-2"
              >
                <v-expansion-panel-header>
                  <v-row
                      align="center"
                      class="spacer"
                      no-gutters
                  >
                    <v-col
                        v-if="message.question"
                        class="text-truncate"
                    >
                      &mdash;
                      {{ message.question }}
                    </v-col>
                  </v-row>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-divider></v-divider>
                  <v-card-text>
                    <p
                        v-for="(item) in message.answer" :key="item.id"
                    >
                      {{ item }}
                    </p>
                  </v-card-text>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-col>
      </v-row>
      <v-row class="text-center" justify="space-around">
        <v-col class="mb-4" cols="6">
          <h1 class="display-2 font-weight-bold mb-3">
            <hr color="#ff0000"/>
          </h1>
        </v-col>
      </v-row>
      <v-row class="text-center" justify="space-around">
        <v-col
            class="mb-5"
            cols="10"
            lg="8"
            md="10"
            sm="10"
            xs="10"

        >
          <v-row justify="center">
            <v-expansion-panels popout>
              <v-expansion-panel
                  hide-actions
                  class="mb-2"
              >
                <v-expansion-panel-header>
                  <v-row
                      align="center"
                      class="spacer"
                      no-gutters
                  >
                    <v-col
                        class="text-truncate"
                    >
                      &mdash;
                      Стоимость услуг
                    </v-col>
                  </v-row>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-divider></v-divider>
                  <v-simple-table>
                    <template v-slot:default>
                      <thead>
                      <tr>
                        <th class="text-left">
                          Услуга
                        </th>
                        <th class="text-right">
                          Цены
                        </th>
                      </tr>
                      </thead>
                      <tbody>
                      <tr
                          v-for="item in prices"
                          :key="item.priceName"
                      >
                        <td>{{ item.priceName }}</td>
                        <td>{{ item.priceValue }}</td>
                      </tr>
                      </tbody>
                    </template>
                  </v-simple-table>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-col>
      </v-row>
      <v-row class="text-center" justify="space-around">
        <v-col
            class="mb-5"
            cols="10"
            lg="8"
            md="10"
            sm="10"
            xs="10"

        >
          <v-row justify="center">
            <v-expansion-panels popout>
              <v-expansion-panel
                  v-for="(wim, i) in whereIsMe"
                  :key="i"
                  hide-actions
                  class="mb-2"
              >
                <v-expansion-panel-header>
                  <v-row
                      align="center"
                      class="spacer"
                      no-gutters
                  >
                    <v-col
                        v-if="wim.question"
                        class="text-truncate"
                    >
                      &mdash;
                      {{ wim.question }}
                    </v-col>
                  </v-row>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-divider></v-divider>
                  <v-card-text>
                    <p
                        v-for="(item) in wim.answer" :key="item.id"
                    >
                      {{ item }}
                    </p>
                  </v-card-text>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-col>
      </v-row>
      <v-col
          class="mb-5"
          cols="12"
      >
        <v-row justify="center" class="mb-4">
          <a
              v-for="(link, i) in importantLinks"
              :key="i"
              :href="link.href"
              class="subheading mx-3"
              target="_blank"
          >
            {{ link.text }}
          </a>
        </v-row>
      </v-col>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: () => ({
    whereIsMe: [
      {
        question: "Где я нахожусь?",
        answer: [
          "Живу м. Щелковская",
          "Езжу по всей Москве",
          "Выезд бесплатный",
        ]
      }
    ],
    messages: [
      {
        question: "Кто я?",
        answer: ["Мне 35 лет.",
          "Родился и живу в Москве, метро Щелковская.",
          "Закончил 11 классов, далее поступил в колледж, получил среднее профессиональное образование по специальности экономика, технология, менеджмент, также есть неоконченное высшее образование. Работал в компании в сфере интернет и телекоммуникаций.",
          "7 лет работал в компьютерной компании, более 18 лет занимаюсь ремонтами и сборками компьютеров ✊🏻",
          "А также я муж и отец прекрасной доченьки!"]
      },
      {
        question: "Что именно я делаю?",
        answer: ["⚙️ Ремонт ноутбуков",
          "⚙️ Ремонт компьютеров",
          "🖥️ Сборка компьютера на заказ",
          "💻 Установка программного обеспечения",
          "🖱️ Удаление вирусов, sms баннеров",
          "💻 Восстановление данных",
          "🖱️ Настройка проводных и беспроводных сетей."]
      },
    ],
    prices: [
      {priceName: "⚙️ Ремонт ноутбуков", priceValue: "От 2000 рублей"},
      {priceName: "⚙️ ️Ремонт компьютеров", priceValue: "От 2000 рублей"},
      {priceName: "⚙️ ️Сборка компьютера", priceValue: "От 3000 рублей до 10000 рублей"},
      {priceName: "⚙️ ️Сборка компьютера", priceValue: "От 3000 рублей до 10000 рублей"},
      {priceName: "💻 Восстановление данных", priceValue: "От 5000 рублей"},
      {priceName: "💻 Настройка интернета", priceValue: "От 1000 рублей"},
      {priceName: "🖱️ Диагностика", priceValue: "Бесплатно"},
      {priceName: "🏎️ Выезд", priceValue: "Бесплатно"},
    ],
    importantLinks: [
      {
        text: 'Договориться о встрече',
        href: 'https://wa.me/79260917171',
      },
      {
        text: 'Задать мне вопрос',
        href: 'https://wa.me/79260917171',
      },
      {
        text: 'Позвонить мне',
        href: 'tel:+79260917171',
      },
      {
        text: 'Примеры моих работ',
        href: 'https://instagram.com/merenkov_nikolai',
      },
    ],
  }),
}
</script>
