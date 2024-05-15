<template>
  <q-page>
    <div>
      <q-icon
        name="icon-mat-search"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-fa-500px-brands"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-ion-md-add-circle-outline"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-eva-activity-outline"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-ti-arrow-up"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-la-accessible-icon"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-mat-settings"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-if-phone"
        size="xl"
        class="q-ma-lg"
      />
      <q-icon
        name="icon-custom-member"
        size="xl"
        class="q-ma-lg"
      />
    </div>

    <q-select
      v-model="model"
      :options="options"
      dropdown-icon="icon-mat-arrow_drop_down"
      label="Filled"
      style="width: 200px;"
      class="q-ma-xl"
      filled
    />

    <div class="q-pa-md">
      <q-date
        v-model="date"
        today-btn
      />
    </div>

    <div class="q-pa-md row items-start q-gutter-md">
      <q-color v-model="hex" class="my-picker" />
    </div>

    <div class="q-pa-lg flex flex-center">
      <q-pagination
        v-model="current"
        :max="5"
        input
      />
    </div>

  <div class="q-pa-md q-gutter-sm">
    <q-editor
      v-model="qeditor"
      :dense="$q.screen.lt.md"
      :toolbar="[
        [
          {
            label: $q.lang.editor.align,
            icon: $q.iconSet.editor.align,
            fixedLabel: true,
            list: 'only-icons',
            options: ['left', 'center', 'right', 'justify']
          },
          {
            label: $q.lang.editor.align,
            icon: $q.iconSet.editor.align,
            fixedLabel: true,
            options: ['left', 'center', 'right', 'justify']
          }
        ],
        ['bold', 'italic', 'strike', 'underline', 'subscript', 'superscript'],
        ['token', 'hr', 'link', 'custom_btn'],
        ['print', 'fullscreen'],
        [
          {
            label: $q.lang.editor.formatting,
            icon: $q.iconSet.editor.formatting,
            list: 'no-icons',
            options: [
              'p',
              'h1',
              'h2',
              'h3',
              'h4',
              'h5',
              'h6',
              'code'
            ]
          },
          {
            label: $q.lang.editor.fontSize,
            icon: $q.iconSet.editor.fontSize,
            fixedLabel: true,
            fixedIcon: true,
            list: 'no-icons',
            options: [
              'size-1',
              'size-2',
              'size-3',
              'size-4',
              'size-5',
              'size-6',
              'size-7'
            ]
          },
          {
            label: $q.lang.editor.defaultFont,
            icon: $q.iconSet.editor.font,
            fixedIcon: true,
            list: 'no-icons',
            options: [
              'default_font',
              'arial',
              'arial_black',
              'comic_sans',
              'courier_new',
              'impact',
              'lucida_grande',
              'times_new_roman',
              'verdana'
            ]
          },
          'removeFormat'
        ],
        ['quote', 'unordered', 'ordered', 'outdent', 'indent'],

        ['undo', 'redo'],
        ['viewsource']
      ]"
      :fonts="{
        arial: 'Arial',
        arial_black: 'Arial Black',
        comic_sans: 'Comic Sans MS',
        courier_new: 'Courier New',
        impact: 'Impact',
        lucida_grande: 'Lucida Grande',
        times_new_roman: 'Times New Roman',
        verdana: 'Verdana'
      }"
    />
    </div>

  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      model: ref(null),
      options: [
        'Google', 'Facebook', 'Twitter', 'Apple', 'Oracle'
      ],
      date: ref('2019/02/01'),
      hex: ref('#FF00FF'),
      current: ref(3),
      qeditor: ref(
        '<pre>Check out the two different types of dropdowns' +
        ' in each of the "Align" buttons.</pre> '
      )
    }
  }
}
</script>