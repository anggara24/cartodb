<template>
  <header class="head-section">
    <div class="head-sectionContainer">
      <h2 class="head-sectionTitle is-txtGrey">
        <span class="icon icon--large"><slot name="icon"></slot></span>
        {{title}}
      </h2>

      <ul class="head-sectionActions">
        <li class="head-sectionActionsItem head-sectionDropdownContainer">
          <slot name="dropdownButton"></slot>
        </li>

        <li class="head-sectionActionsItem" v-if="!!$slots.actionButton">
          <slot name="actionButton"></slot>
        </li>
      </ul>
    </div>

    <p v-if="description" class="head-sectionDescription">{{description}}</p>
  </header>
</template>

<script>
export default {
  name: 'SectionTitle',
  props: {
    title: String,
    description: String,
    showActionButton: Boolean
  }
};
</script>

<style scoped lang="scss">
@import 'stylesheets/new-dashboard/variables';

.icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 18px;
  height: 18px;
}

.icon--large {
  width: 24px;
  height: 24px;
}

.icon--small {
  width: 14px;
  height: 14px;
}

.head-section {
  margin-bottom: 36px;
}

.head-sectionTitle {
  display: flex;
  align-items: center;
  color: $text-color;
  font: 700 24px/1.6 'Montserrat';

  .icon {
    margin-right: 16px;
    margin-left: -40px;
  }
}

.head-sectionDescription {
  color: $text-color;
  font: 400 16px/1.6 'Open Sans';

  a {
    color: $text-color;
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
}

.head-sectionContainer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 8px;
}

.head-sectionActions {
  display: flex;
  align-items: center;
}

.head-sectionActionsItem {
  margin-right: 32px;

  &:last-child {
    margin-right: 0;
  }
}

.head-sectionDropdownContainer {
  position: relative;

  &:hover {
    .head-sectionDropdown {
      opacity: 1;
      pointer-events: all;
    }
  }
}
</style>
