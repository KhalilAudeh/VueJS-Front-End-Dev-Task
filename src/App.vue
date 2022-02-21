<template>
  <div class="container-fluid text-center my-5 proxima-nova-regular">
    <!-- for content before the blocks list -->
    <div class="row">
      <div class="col">
        <h2 class="text-capitalize d-none d-md-block gotham-bold">
          experienced &amp; multi-talented
        </h2>
        <h3 class="text-capitalize d-block d-md-none gotham-bold">
          experienced &amp; multi-talented
        </h3>
      </div>
    </div>

    <div class="row">
      <div class="col-3 col-md-1 m-auto">
        <hr class="border" />
      </div>
    </div>

    <div class="row mt-2">
      <div class="col-8 col-md-6 p-0 m-auto">
        <p class="colored-text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
          tortor leo, porttitor vel dictum at, aliquam et augue. Duis vel
          molestie risus, ut lobortis felis.
        </p>
      </div>
    </div>

    <!-- blocks list -->
    <div class="row mt-5">
      <div
        class="col-10 col-sm-6 col-md-4 col-lg-3 p-4 m-auto"
        v-for="(block, index) in blocks_list"
        :key="index"
      >
        <div class="row block-img py-4 rounded-top">
          <div class="col">
            <img src="./assets/info.png" alt="" />
          </div>
        </div>

        <div class="row block-info py-4">
          <div class="col-12 gotham-bold text-uppercase">
            <h6>{{ block.title }}</h6>
          </div>

          <div class="col-12 px-4 colored-text">
            <p>{{ block.content }}</p>
          </div>

          <div class="col-1 p-0 m-auto plus-sign rounded-circle">
            <span @click="readMore($event, index)">&plus;</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      blocks_list: [
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          title: "block",
          content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
      ],
      isFull: false,
    };
  },

  methods: {
    readMore(event, index) {
      if (event.target.innerText == "+") {
        event.target.innerText = "-";

        this.blocks_list[index].content =
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut vestibulum eros nisi, eu sagittis nisl feugiat quis.";
      } else {
        event.target.innerText = "+";

        this.blocks_list[index].content =
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit.";
      }
    },
  },
};
</script>

<style>
@font-face {
  font-family: "Gotham-Bold";
  src: local("Gotham-Bold"), url(./fonts/Gotham-Bold.ttf) format("truetype");
}

@font-face {
  font-family: "ProximaNova-Regular";
  src: local("ProximaNova-Regular"),
    url(./fonts/ProximaNova-Regular.ttf) format("truetype");
}

.gotham-bold {
  font-family: "Gotham-Bold";
}

.proxima-nova-regular {
  font-family: "ProximaNova-Regular";
}

body {
  color: white !important;
  background-color: #1c2026 !important;
}

.colored-text {
  color: #65757e;
}

.block-img {
  background-color: #57665f;
}

.block-info {
  background-color: black;
}

.plus-sign {
  background-color: #1c2026 !important;
  font-size: 1.25rem;
  cursor: pointer;
}
</style>
