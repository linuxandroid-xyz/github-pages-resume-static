<template>
<div>
    <!-- <a class="" href="#">english</a> -->

    <a v-if="$store.state.lang==='en'" @click="handleLang" class="language-buttom" href="#">فارسی</a>
    <a v-else @click="handleLang" class="language-buttom" href="#">english</a>
    <div class="cool-img-bg">
        <div id="top-section-id" class="container transparent-black">
            <div class="top-border">
                <div v-if="$store.state.lang==='en'">
                <h2 class="title">Yosef Salmalian</h2>
                <p class="subtitle">Web developer and fast learner</p>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h2 class="title">یوسف سلملیان</h2>
                    <p class="subtitle">توسعه دهنده بکند و فرانت اند</p>
                </div>
            </div>
        </div>
    </div>
<!--     <h1>below is star?</h1>
    <i class="fa fa-fw fa-star-o"></i> -->
    <slide-bar id="burger-slider-id" :navPermistion="nav_bg_permistion" :disableEsc="true" :right="true">
            <a @click="scrollVanilla" :class="{ active: in_top_section }" href="#top-section-id">
                <div v-if="$store.state.lang==='en'">top</div>
                <div v-if="$store.state.lang==='fa'">برو بالا</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_top_section && in_about_section }" href="#about-section-id">
                <div v-if="$store.state.lang==='en'">about</div>
                <div v-if="$store.state.lang==='fa'">درباره من</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_about_section && in_skills_section }" href="#skills-section-id">
                <div v-if="$store.state.lang==='en'">skills</div>
                <div v-if="$store.state.lang==='fa'">مهارت ها</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_skills_section && in_experience_section }" href="#experience-section-id">
                <div v-if="$store.state.lang==='en'">experience</div>
                <div v-if="$store.state.lang==='fa'">سابقه</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_experience_section && in_education_section }" href="#education-section-id">
                <div v-if="$store.state.lang==='en'">education</div>
                <div v-if="$store.state.lang==='fa'">تحصیلات</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_education_section && in_portfolio_section }" href="#portfolio-section-id">
                <div v-if="$store.state.lang==='en'">portfolio</div>
                <div v-if="$store.state.lang==='fa'">کار های من</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_portfolio_section && in_contact_section }" href="#contact-section-id">
                <div v-if="$store.state.lang==='en'">contact</div>
                <div v-if="$store.state.lang==='fa'">تماس با من</div>
            </a>

    </slide-bar>
    <div class="nav-place-holder">
        <div id="dynamic-nav-bar-id" class="dynamic-nav-bar">
            <a @click="scrollVanilla" :class="{ active: in_top_section }" href="#top-section-id">
                <div v-if="$store.state.lang==='en'">top</div>
                <div v-if="$store.state.lang==='fa'">برو بالا</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_top_section && in_about_section }" href="#about-section-id">
                <div v-if="$store.state.lang==='en'">about</div>
                <div v-if="$store.state.lang==='fa'">درباره من</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_about_section && in_skills_section }" href="#skills-section-id">
                <div v-if="$store.state.lang==='en'">skills</div>
                <div v-if="$store.state.lang==='fa'">مهارت ها</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_skills_section && in_experience_section }" href="#experience-section-id">
                <div v-if="$store.state.lang==='en'">experience</div>
                <div v-if="$store.state.lang==='fa'">سابقه</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_experience_section && in_education_section }" href="#education-section-id">
                <div v-if="$store.state.lang==='en'">education</div>
                <div v-if="$store.state.lang==='fa'">تحصیلات</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_education_section && in_portfolio_section }" href="#portfolio-section-id">
                <div v-if="$store.state.lang==='en'">portfolio</div>
                <div v-if="$store.state.lang==='fa'">کار های من</div>
            </a>
            <a @click="scrollVanilla" :class="{ active: !in_portfolio_section && in_contact_section }" href="#contact-section-id">
                <div v-if="$store.state.lang==='en'">contact</div>
                <div v-if="$store.state.lang==='fa'">تماس با من</div>
            </a>


        </div>
    </div>
    <!-- <div id="hidden-bg-id" class="hidden-bg"></div> -->
    <div id="about-section-id" class="container-dynamic about-bg">
        <div class="context-container">
            <div class="context-header">
                <h1 class="white-text">
                    <div v-if="$store.state.lang==='en'">about me</div>
                    <div v-if="$store.state.lang==='fa'"  style="margin-bottom: 5px;">درباره من</div>
                </h1>
                <h5 class="white-text">
                    <div v-if="$store.state.lang==='en'">A small intrudoction about my self</div>
                    <div v-if="$store.state.lang==='fa'">توضیحات خلاصه در باره خودم</div>
                </h5>
            </div>
            <div class="context-content">
                <div v-if="$store.state.lang==='fa'" class="about-content-img">
                    <img src="~/static/me.jpg" alt="my picture">
                </div>
                <div class="about-content-about" :class="{ rtl: $store.state.lang==='fa' }">
                    <div v-if="$store.state.lang==='en'">
                        <h2 class="white-text">Yosef Salmalian</h2>
                        <h4 class="white-text">Full Stack Web Developer</h4>
                        <p class="white-text">
                            I am a curious and an active programmer, looking to learn and experience new things, I do not believe in talent and I think that everybody can learn what they want if they take the time for it
                        </p>
                        <p class="white-text">
                           I am a student now so I can do freelancing and part-time works, if you are interested, send me a message 
                        </p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <h2 class="white-text">یوسف سلملیان</h2>                        
                        <h4 class="white-text">توسعه دهنده فول استک وب</h4>
                        <p class="white-text">
                            من یک برنامه نویس کنجکاو و فعال هستم، به دنبال یادگیری و تجربه چیز های جدیدم، من به استعداد معتقد نیستم و فکر میکنم که هر کسی میتونه اون چیزی که براش وقت میزاره رو یاد بگیره
                        </p>

                        <p class="white-text">
                            من چون که در حال تحصیل هستم میتونم کارهای پارت تایم و دور کاری انجام بدم اگه علاقه مندین میتونین به من پیام بدین
                        </p>
                    </div>
                </div>
                <div v-if="$store.state.lang==='en'" class="about-content-img">
                    <img src="~/static/me.jpg" alt="تصیور من">
                </div>
            </div>
        </div>

    </div>
    <div id="skills-section-id" class="container-dynamic">
        <div class="context-container">
            <div class="context-header">
                <div v-if="$store.state.lang==='en'">
                    <h1>TECHNICAL SKILLS</h1>
                    <h5>That I can say i'm good at</h5>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h1 style="margin-bottom:5px;">مهارت های من</h1>
                    <h5>که میتونم بگم در انجامشون خوب عمل میکنم</h5>
                </div>
            </div>
            <div class="context-content">

                <h2 v-if="$store.state.lang==='en'" class="content-about-divider">Programming Languages</h2>
                <h2 v-if="$store.state.lang==='fa'"  class="content-about-divider">زبان های برنامه نویسی</h2>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="70"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Python</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>my first programming experience</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>اولین زبانی که باهاش برنامه نویسی کردم</p>
                    </div>
                </div>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="55"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Java Script</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>every where language</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>زبان عالی و همه جانبه</p>
                    </div>
                </div>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="55"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>C</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>robust and super fast</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>سریع ترین زبان و پایه تمام سیستم عامل ها</p>
                    </div>
                </div>
                <h2 v-if="$store.state.lang==='en'" class="content-about-divider">Frameworks</h2>
                <h2 v-if="$store.state.lang==='fa'"  class="content-about-divider">فریم ورک ها</h2>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="60"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Django</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>popular and secure backend framework</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>فریم ورک سریع برای بکند با پایتون</p>
                    </div>
                </div>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="50"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Vue.js</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>new and trend frontend framework</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>تکنولوژی جدید و کامپوننت بیس فرانت اند</p>
                    </div>
                </div>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="60"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Telegraf.js</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>modert telegram bot framework</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>فریم ورک توسعه بات های تلگرام</p>
                    </div>
                </div>
                <h2 v-if="$store.state.lang==='en'" class="content-about-divider">Packages & Libraries</h2>
                <h2 v-if="$store.state.lang==='fa'"  class="content-about-divider">کتاب خانه ها و پکیج ها</h2>
                <div class="circular-item">
                    <radial-progress
                        :diameter="180"
                        :total-steps="totalSteps"
                        :toComplete="70"
                        :fillTimeOut="1"
                    >
                    </radial-progress>
                    <h2>Telethon</h2>
                    <div v-if="$store.state.lang==='en'">
                        <p>telegram client api</p>
                    </div>
                    <div v-if="$store.state.lang==='fa'">
                        <p>برای کار با بخش کلاینت ای پی آی تلگرام</p>
                    </div>
                </div>
<!--                 <vue-ellipse-progress 
                      :colorFill="red"
                      :data="circles"                    
                      :progress="40"
                      :lineMode="normal"
                      :angle="-90"
                      emptyColor="#ccc"
                      :thickness="14"
                      emptyThickness="5%"
                      :legend="true"
                      animation="bounce 1200 1000"
                      fontColor="#474d5d"
                      dot="10 blue"
                      fontSize="3rem"
                      >
                      
                      <span slot="legend-value">%</span>
                      <p slot="legend-caption"></p>
                      
                </vue-ellipse-progress> -->

                <h4 v-if="$store.state.lang==='en'" style="text-align: left;" class="content-about-divider divider-attention">Attention</h4>
                <h4 v-if="$store.state.lang==='fa'" style="margin-bottom: 10px;text-align: right;" class="content-about-divider divider-attention">توضیح</h4>
                <p v-if="$store.state.lang==='en'" style="text-align: left;" class="about-attenction divider-attention">
                    These progress bars are very cool but I don't mean that I know 50% of a language, what I mean is 30 - 50% is where you have learned basics and have done tutorial projects,  50 - 70% is where you have a lot working and doing some deep thinking on it.
                </p>
                <p v-if="$store.state.lang==='fa'" style="text-align: right;" class="about-attenction divider-attention">
                    این نوار پیشرفت ها رو برای زیبایی گزاشتم، و منظورم این نیست که من ۷۰٪ یک زبان رو میدونم. منظور من اینه که بین ۳۰-۵۰٪ پروژه های آموزشی انجام دادم و با پایه آشنا هستم. و بین ۵۰ - ۷۰٪ جاییه که وقت زیادی روش گزاشتم و همچنین پروژه های کوچکی انجام دادم
                </p>
            </div>
        </div>
    </div>
    <div id="experience-section-id" class="container-dynamic">
        <div class="context-container">
            <div class="context-header">
                <div v-if="$store.state.lang==='en'">
                    <h1>work experience</h1>
                    <h5>my previous associations</h5>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h1 style="margin-bottom:5px;">تجربه کاری</h1>
                    <h5>تجربه های کاری من در گذشته</h5>
                </div>
            </div>
            <div class="context-content">
                <div class="card-item">
                    <div class="date-item-float">
                        <div class="circle-date-item">
                            <div class="top-space"></div>
                            <div v-if="$store.state.lang==='en'">
                                <h5>February, 2020</h5>
                                <h5>present</h5>
                            </div>
                            <div v-if="$store.state.lang==='fa'">
                                <h5>اسفند، ۱۳۹۸</h5>
                                <h5>حال حاضر</h5>
                            </div>
                        </div>
                    </div>
                    <div class="arrow-container">
                        <div class="arrow-shape"></div>
                    </div>
                    <div class="card-contain"> 
                        <div class="card" style="margin:10px;">
                            <div v-if="$store.state.lang==='en'" style="text-align: left; margin-left: 30px;">
                                <h3>frelancing</h3>
                                <p>doing freelancing projects like telegram bots.</p>
                            </div>
                            <div v-if="$store.state.lang==='fa'" style="text-align: right; margin-right: 30px;">
                                <h3>فریلنسر</h3>
                                <p>انجام پروژه های کوچک از جاهای مختلف، از کانال های پروژه و پونیشا، نوشتن بات های تلگرامی و غیره</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div id="education-section-id" class="container-dynamic">
        <div class="context-container">
            <div class="context-header">
                <div v-if="$store.state.lang==='en'">
                    <h1>educations & diplomas</h1>
                    <h5>what I have done in my academic career</h5>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h1 style="margin-bottom:5px;">تحصیلات و آموزش ها</h1>
                    <h5>تحصیلات و آموزش هایی که من گرفتم</h5>
                </div>
            </div>
            <div class="context-content">
                <div class="card-item">
                    <div class="date-item-float">
                        <div class="circle-date-item">
                            <div class="top-space"></div>
                            <div v-if="$store.state.lang==='en'">
                                <h5>septamber, 2017</h5>
                                <h5>present</h5>
                            </div>
                            <div v-if="$store.state.lang==='fa'">
                                <h5>مهر، ۱۳۹۶</h5>
                                <h5>حال حاضر</h5>
                            </div>
                        </div>
                    </div>
                    <div class="arrow-container">
                        <div class="arrow-shape"></div>
                    </div>
                    <div class="card-contain">
                        <div class="card" style="margin:10px;">
                            <div v-if="$store.state.lang==='en'" style="text-align: left; margin-left: 30px;">
                                <h3>a computer engineering student at Ferdowsi university </h3>
                                <p>still learning at university, passed computer networks & operating systems & advanced programming with good result</p>
                            </div>
                            <div v-if="$store.state.lang==='fa'" style="text-align: right; margin-right: 30px;">
                                <h3>مهندسی کامپیوتر، دانشگاه فردوسی مشهد</h3>
                                <p>در حال تحصیل در رشته مهندسی کامپیوتر هستم و همچنین درس های شبکه های کامپیوتری و سیستم های عامل و برنامه نویسی پیشرفته را با نمره خوب گذرانده ام</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div id="portfolio-section-id" class="container-dynamic">
        <div class="context-container">
            <div class="context-header">
                <div v-if="$store.state.lang==='en'">
                    <h1>PORTFOLIO</h1>
                    <h5>Show case of my works</h5>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h1 style="margin-bottom:5px;">نمونه کارها</h1>
                    <h5>تعدای از نمونه کار های من و توضیحاتی خلاصه در مورد آنها</h5>
                </div>

            </div>
            <div class="context-content">
                <div v-if="$store.state.lang==='en'">
                    <p>Going to Add this in future</p> 
                    <p>this single page static web application is writen in vue.js using nuxt.js framework</p>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <p>بعدا اضاف خواهد شد</p>
                    <p>همین وب سایت با استفاده از ویو جی اس و نوکست جی اس نوشته شده است</p>
                </div>
            </div>
        </div>
    </div>
    <div id="contact-section-id" class="container-dynamic">
        <div class="context-container">
            <div class="context-header">
                <div v-if="$store.state.lang==='en'">
                    <h1>get in touch</h1>
                    <h5>please feel free if you whould like to have a chat</h5>
                </div>
                <div v-if="$store.state.lang==='fa'">
                    <h1 style="margin-bottom:5px;">با من تماس بگیرید</h1>
                    <h5>راه های ارتباطی تا بتونید با هم صجبت کنیم</h5>
                </div>

            </div>
            <div class="context-content">
                <div class="google-container">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3215.095871522228!2d59.52744881550642!3d36.3099819028393!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3f6c925d73674337%3A0x6325879f5fb01d18!2sFerdowsi%20University%20of%20Mashhad!5e0!3m2!1sen!2spl!4v1590845979554!5m2!1sen!2spl" 
                        width="100%" 
                        height="450" 
                        frameborder="0" 
                        style="padding:0;margin:0;border-top: 0.5vh dashed #2e9878; border-bottom: 0.5vh dashed #2e9878;" 
                        allowfullscreen="no" 
                        aria-hidden="false" 
                        tabindex="0"
                        scrolling="no"
                    ></iframe>
                </div>
                <div class="address-content-bg">
                <div class="address-content">
                    <div class="contact-details">
                        <div class="small-center">
                            <div v-if="$store.state.lang==='en'">
                                <h1>contact details</h1>

                            </div>
                            <div v-if="$store.state.lang==='fa'" style=" margin-bottom: 10px;">
                                <h1>اطلاعات تماس</h1>
                            </div>
                            <hr style="margin-bottom: 20px;">
                            <div class="icon-container">
                                <phone-solid-icon></phone-solid-icon>
                                <p>+989154164897</p>
                            </div>
                            <div class="icon-container">
                                <envelope-solid-icon></envelope-solid-icon>
                                <p>flaslnm@gmail.com</p>
                            </div>
                        </div>
                    </div>
                </div>
                </div>
                <div class="buttom-bg">
                    <a @click="handleRedirect" href="https://github.com/usefss">
                        <v-icon @mouseover="handleZoom('github')" class="github-i" v-bind:scale="iconScale.github" name="brands/github"></v-icon>
                    </a>
                    <a @click="handleRedirect" href="https://gitlab.com/usefss">
                        <v-icon @mouseover="handleZoom('gitlab')" class="gitlab-i" v-bind:scale="iconScale.gitlab" name="brands/gitlab"></v-icon>
                    </a>
                    <a @click="handleRedirect" href="https://t.me/THEyosefs">
                        <v-icon @mouseover="handleZoom('telegram')" class="telegram-i" v-bind:scale="iconScale.telegram" name="brands/telegram"></v-icon>
                    </a>
                    <!-- <font-awesome-icon icon="coffee" /> -->
                    <!-- <font-awesome-icon icon="external-link" /> -->

                    <!-- <v-icon name="brands/external-link" /> -->

                </div>
            </div>
        </div>
    </div>
    <!-- <qutii/> -->
</div>
</template>

<script>
import RadialProgress from '~/components/RadialProgress'
import MenuBar from '~/components/MenuBar'
import SlideBar from '~/components/SlideBar'
import PhoneSolidIcon from '~/components/icons/PhoneSolidIcon'
import EnvelopeSolidIcon from '~/components/icons/EnvelopeSolid'

window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());

gtag('config', 'G-EGFW7EJ9BC');

export default {
    components: {
        'radial-progress': RadialProgress,
        'slide-bar': SlideBar,
        'menu-bar': MenuBar,
        'phone-solid-icon': PhoneSolidIcon,
        'envelope-solid-icon': EnvelopeSolidIcon,
        // 'qutii': Qutii
        // 'v-icon': Icon
    },
    data () {
        return {
            iconScale: {
                github: 4,
                gitlab: 3,
                telegram: 3,
            },
            nav_bg_permistion: false,
            completedSteps: 70,
            totalSteps: 100,
            lang: 'fa',
            in_top_section: null,
            in_about_section: null,
            in_skills_section: null,
            in_experience_section: null,
            in_education_section: null,
            in_portfolio_section: null,
            in_contact_section: null
        }
    },
    mounted: function() {
        if (
            process.client &&
            "IntersectionObserver" in window &&
            "IntersectionObserverEntry" in window && 
            "intersectionRatio" in window.IntersectionObserverEntry.prototype
        ){
            this.handleObservers()
        }

        window.addEventListener('scroll', this.handleScroll)
        try{
            window.scrollTo({
                top: this.$store.state.Ypos,
                behavior: 'smooth'
            })
        } catch (err) {
            console.log(err)
        }
    },
    watch: {
    },
    methods: {
        handleLang(event) {
            event.preventDefault()
            if (event.target.innerHTML === 'فارسی')
                this.$store.commit('setLang', 'fa')
            else if (event.target.innerHTML === 'english')
                this.$store.commit('setLang', 'en')
        },
        handleZoom(target) {
            console.log(this.iconScale[target])
            if (this.iconScale[target] != 4){
                for (let i in this.iconScale) {
                    if (i !== target) {
                        this.iconScale[i] = 3
                    }
                }
                this.iconScale[target] = 4
                // setTimeout(() => {
                //     this.iconScale[target] = 3
                // }, 2000)
            }
        },
        handleRedirect(event) {
            event.preventDefault()
            // console.log(event.target.closest('a').getAttribute('href'))
            window.open(event.target.closest('a').getAttribute('href'), '_blank')
        },
        handleScroll(event) {
            this.$store.commit('setYpos', window.scrollY)
        },
        scrollVanilla(event) {
            event.preventDefault()
            let el = document.querySelector(
                event.target.closest('a').getAttribute('href')
            )
            let bodyRect = document.body.getBoundingClientRect().top
            let elRect = el.getBoundingClientRect().top
            window.scrollTo({
                top: (elRect - bodyRect + 1),
                behavior: 'smooth'
            })
        },
        handleObservers() {
            new IntersectionObserver(entries => {
                this.in_top_section = entries[0].isIntersecting
                let nav_el = document.querySelector('#dynamic-nav-bar-id')
                let hidden_top = document.querySelector('#hidden-nav-bar-id')
                if (this.in_top_section) {
                    this.nav_bg_permistion = false
                    // if (!this.nav_bg_permistion)
                    // document.querySelector('#hidden-bg-id')
                    //     .style.display = 'none'
                    nav_el.style.position = 'relative'
                    nav_el.style.top = 'auto'
                } else {
                    this.nav_bg_permistion = true
                    // if (this.nav_bg_permistion)
                    //     document.querySelector('#hidden-bg-id')
                    //         .style.display = 'block'
                    nav_el.style.position = 'fixed'
                    nav_el.style.top = '0'
                }
                // console.log('top')

            }).observe(
                document.querySelector('#top-section-id')
            )

            new IntersectionObserver(entries => {
                this.in_about_section = entries[0].isIntersecting
                // console.log('about')
            }).observe(
                document.querySelector('#about-section-id')
            )

            new IntersectionObserver(entries => {
                this.in_skills_section = entries[0].isIntersecting
                // console.log('skills')
            }).observe(
                document.querySelector('#skills-section-id')
            )
            new IntersectionObserver(entries => {
                this.in_experience_section = entries[0].isIntersecting
                // console.log('experience')
            }).observe(
                document.querySelector('#experience-section-id')
            )
            new IntersectionObserver(entries => {
                this.in_education_section = entries[0].isIntersecting
                // console.log('education')
            }).observe(
                document.querySelector('#education-section-id')
            )
            new IntersectionObserver(entries => {
                this.in_portfolio_section = entries[0].isIntersecting
                // console.log('portfolio')
            }).observe(
                document.querySelector('#portfolio-section-id')
            )
            new IntersectionObserver(entries => {
                this.in_contact_section = entries[0].isIntersecting
                // console.log('contact')
            }).observe(
                document.querySelector('#contact-section-id')
            )
        }
    }
}
</script>

<style lang="scss">
// @import "~/assets/styles.scss"
</style>
