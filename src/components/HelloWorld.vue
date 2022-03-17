<template>
  <v-container class="d-flex justify-center">
    <v-col cols="10" xl="8" lg="10">
      <v-expansion-panels focusable>
        <v-expansion-panel v-for="(task, index) in tasks" :key="index">
          <v-expansion-panel-header
            >zadanie {{ task.Section }}.{{
              task.Number
            }}</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <v-card class="mt-6" flat>
              <v-card-title> {{ task.Title }} </v-card-title>
              <v-card-text>
                {{ task.Content }}
              </v-card-text>
            </v-card>
            <v-card flat v-if="task.inputComponent">
              <v-card-title> Dane wejściowe </v-card-title>
              <v-card-subtitle>
                Podaj dane wejściowe do przetworzenia przez serwer (w ramach
                zadania)
              </v-card-subtitle>
              <v-card-text>
                <inputComponent :inputs="task.inputValues" />
              </v-card-text>
            </v-card>
            <v-card class="" max-width="" flat>
              <v-card-title> Kod źródłowy rozwiązania </v-card-title>
              <v-card-text>
                <taskSourceCode />
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-col>
  </v-container>
</template>

<script>
import taskSourceCode from "./taskSourceCode.vue";
import inputComponent from "./inputComponent.vue";
export default {
  name: "HelloWorld",
  components: {
    taskSourceCode,
    inputComponent,
  },
  methods: {
    test() {
      alert("XD");
    },
  },
  data: () => ({
    tasks: [
      {
        Section: 1,
        Number: 1,
        Title: "Pitagoras",
        Content:
          "Napisz program, który będzie zawierał trzy zmienne typu int z przypisanymi wartościami większymi od zera. Następnie niech program sprawdzi, czy liczby te spełniają twierdzenie Pitagorasa. Uwaga! Liczby nie muszą być ułożone w kolejności rosnącej.",
        inputComponent: true,
        inputValues: [
          {
            placeholder: "Bok numer 1",
          },
          {
            placeholder: "Bok numer 2",
          },
          {
            placeholder: "Bok numer 3",
          }
        ],
        outputReady: false
      },
      {
        Section: 1,
        Number: 2,
        Title: "Dni Tygodnia",
        Content:
          "Napisz program, który wypisze słownie dzień tygodnia na podstawie liczby wpisanej w zmiennej (np. 1 - poniedziałek, 2 - wtorek itp). Użyj instrukcji switch",
        ComponentPath: "",
      },
      {
        Section: 1,
        Number: 3,
        Title: "Dni Miesiąca",
        Content:
          "Napisz program, który na podstawie zmiennych, zawierających nr miesiąca i roku odpowie, ile dni ma dany miesiąc. Użyj instrukcji warunkowych if, else if, else. Pamiętaj o latach przestępnych.",
        ComponentPath: "",
      },
      {
        Section: 2,
        Number: 1,
      },
      {
        Section: 2,
        Number: 2,
      },
      {
        Section: 2,
        Number: 3,
      },
      {
        Section: 2,
        Number: 4,
      },
      {
        Section: 2,
        Number: 5,
      },
    ],
  }),
};
</script>
