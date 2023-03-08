<template>
  <div class="user">
    <div class="user__img-box">
      <img
        class="user__img"
        src="https://avatars.githubusercontent.com/u/3438503?v=4"
        alt="Fernando" />
      <span class="user__img-username">@Klerith</span>
    </div>
    <div class="user__description">
      <h2 class="user__description-name">Fernando</h2>
      <p class="user__description-text">
        <!-- también se tiene que mostrar un msg si no tiene descripción -->
        Un simple desarrollador :)
      </p>
    </div>
    <div class="user__info">
      <div class="user__info-item">
        <p>repos</p>
        <span>429</span>
      </div>
      <div class="user__info-item">
        <p>seguidores</p>
        <span>9144</span>
      </div>
      <div class="user__info-item">
        <p>siguiendo</p>
        <span>0</span>
      </div>
    </div>

    <div class="user__social">
      <div class="user__social-item">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          viewBox="0 0 20 20"
          fill="currentColor">
          <path
            fill-rule="evenodd"
            d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z"
            clip-rule="evenodd" />
        </svg>
        <span>Costa Rica</span>
      </div>
      <div class="user__social-item">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          viewBox="0 0 20 20"
          fill="currentColor">
          <path
            fill-rule="evenodd"
            d="M12.586 4.586a2 2 0 112.828 2.828l-3 3a2 2 0 01-2.828 0 1 1 0 00-1.414 1.414 4 4 0 005.656 0l3-3a4 4 0 00-5.656-5.656l-1.5 1.5a1 1 0 101.414 1.414l1.5-1.5zm-5 5a2 2 0 012.828 0 1 1 0 101.414-1.414 4 4 0 00-5.656 0l-3 3a4 4 0 105.656 5.656l1.5-1.5a1 1 0 10-1.414-1.414l-1.5 1.5a2 2 0 11-2.828-2.828l3-3z"
            clip-rule="evenodd" />
        </svg>
        <a
          class="user__link-blog"
          href="https://www.udemy.com/user/550c38655ec11/"
          target="_blank"
          >{{ 'https://www.udemy.com/user/550c38655ec11/' }}</a
        >
        <!-- mostrar este párrafo si no tiene link hacia github -->
        <!-- <p>url no definido</p> -->
      </div>
    </div>
    <a
      href="https://github.com/Klerith"
      target="_blank"
      rel="noopener noreferrer"
      class="btn-link btn-primary"
      >ver GitHub</a
    >
  </div>
</template>

<script setup>
  // usar este objeto reactivo y pintarlo en el html
  const user = {
    avatar_url: 'https://avatars.githubusercontent.com/u/1561955?v=4', //image
    login: 'midudev', //username
    name: 'Miguel Ángel Durán',
    bio: 'Te enseño Programación y Desarrollo Web. Creador de contenido en Twitch y YouTube.',
    public_repos: 178,
    followers: 11212,
    following: 2,
    blog: '', //website
    location: 'Barcelona',
    html_url: 'https://github.com/midudev', //link de github
  };
  console.log(user);
</script>

<style scoped>
  .user {
    max-width: 30rem;
    width: 100%;
    padding: 1.2rem;
    background-color: var(--secondary400);
    border-radius: 0.5rem;
    box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.1);
  }
  @media (min-width: 768px) {
    .user {
      width: auto;
      min-width: 25rem;
    }
  }
  .user__img-box {
    width: 100%;
    border-radius: 0.5rem;
    overflow: hidden;
    height: 20rem;
    position: relative;
  }
  .user__img {
    width: 100%;
    height: 20rem;
    object-fit: cover;
  }
  .user__img-username {
    font-size: 0.9rem;
    display: block;
    position: absolute;
    padding: 0.2rem 0.8rem 0.2rem 0.6rem;
    border-radius: 0.3rem;
    bottom: 1rem;
    right: -0.3rem;
    background-color: hsla(218, 23%, 16%, 0.539);
    border: 1px solid var(--secondary500);
    color: var(--secondary200);
  }

  .user__description {
    text-align: center;
    font-weight: 400;
    color: var(--secondary100);
    padding: 1rem;
  }
  .user__description-name {
    color: var(--secondary100);
    text-transform: capitalize;
    padding-bottom: 0.5rem;
  }
  .user__description-text {
    color: var(--secondary200);
  }
  .user__info {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    background-color: var(--secondary500);
    gap: 0.5rem;
    padding: 0.5rem;
    border-radius: 0.4rem;
  }
  .user__info-item {
    display: flex;
    color: var(--secondary200);
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
  }
  .user__info-item:not(:first-child):before {
    content: '';
    border-radius: 1rem;
    display: block;
    width: 2px;
    height: 100%;
    background-color: var(--secondary400);
    position: absolute;
    left: calc(0rem - 0.3rem);
  }
  .user__info-item p {
    font-size: 0.9rem;
  }
  .user__info-item span {
    font-size: 1.25rem;
    margin-top: 0.2rem;
    font-weight: 800;
    color: var(--secondary100);
  }

  .user__social {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 0.8rem 0;
  }
  .user__social-item {
    display: flex;
    align-items: center;
  }
  .user__social-item:not(:first-child) {
    padding-top: 0.3rem;
  }
  .user__social-item svg {
    width: 1.2rem;
    margin-right: 0.5rem;
  }

  /* enlaces */
  .user__link-blog {
    text-decoration: none;
    color: var(--primary);
  }

  .btn-link {
    width: 100%;
    display: block;
    text-align: center;
    font-weight: 700;
    text-transform: uppercase;
    padding: 0.8rem 1rem;
    border-radius: 0.5rem;
    border: none;
    font-size: 1rem;
    transition: all 0.2s ease-in-out;
    text-decoration: none;
  }
  .btn-link:hover {
    box-shadow: 0px 0px 10px 2px var(--primary);
  }
  .btn-primary {
    color: var(--secondary500);
    background-color: var(--primary);
  }
</style>
