<template>
  <div class="wrapper">
    <div class="accordeon">
      <AccordeonItem :title="'The analysis'">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vel doloribus sequi id quam omnis sit dignissimos
          exercitationem libero reprehenderit tenetur sapiente dolores, atque architecto nobis earum alias saepe
          corrupti quas!
        </p>
      </AccordeonItem>

      <AccordeonItem :title="'To take into account on user level data'">
        <ul>
          <li>Do you have one user in more than one variant of the same AB test?</li>
          <li>Are you users actually getting the treatment we expect them to get?</li>
          <li>Do we have enough users in our AB test? Are those users representative for the total population?</li>
        </ul>
      </AccordeonItem>

      <AccordeonItem :title="'Our data'">
        <ul>
          <li>Do you have one user in more than one variant of the same AB test?</li>
          <li>Are you users actually getting the treatment we expect them to get?</li>
          <li>Do we have enough users in our AB test? Are those users representative for the total population?</li>
        </ul>
      </AccordeonItem>

      <AccordeonItem :title="'Hands on analyzing'">
        <ul>
          <li>Do you have one user in more than one variant of the same AB test?</li>
          <li>Are you users actually getting the treatment we expect them to get?</li>
          <li>Do we have enough users in our AB test? Are those users representative for the total population?</li>
        </ul>
      </AccordeonItem>

      <AccordeonItem :title="'Initialization'">
        <ul>
          <li>Do you have one user in more than one variant of the same AB test?</li>
          <li>Are you users actually getting the treatment we expect them to get?</li>
          <li>Do we have enough users in our AB test? Are those users representative for the total population?</li>
        </ul>
      </AccordeonItem>
    </div>
  </div>
</template>

<script>
import AccordeonItem from "@/components/Item";
export default {
  components: {
    AccordeonItem,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@600;800&display=swap");

body {
  font-family: "Montserrat", sans-serif;
  line-height: 24;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 8px 0 0;

  li {
    margin-bottom: 8px;
    position: relative;
    padding-left: 20px;
    line-height: 24px;

    &::before {
      content: "";
      width: 10px;
      height: 10px;
      border: 2px solid #2b41b7;
      border-radius: 50%;
      position: absolute;
      left: 0;
      top: 3px;
    }

    &:last-child {
      margin: 0;
    }
  }
}

.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>
