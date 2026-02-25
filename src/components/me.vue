<template>
  <div class="app" :class="{ dark: isDark }">
    <!-- 1. 顶部导航（固定+响应式） -->
    <nav class="nav">
      <div class="container">
        <div class="nav-left">
          <h1>XXX（你的名字）</h1>
          <p class="nav-subtitle">前端开发工程师</p>
        </div>
        <div class="nav-right">
          <button @click="isDark = !isDark" class="theme-btn">
            {{ isDark ? '☀️ 亮色' : '🌙 暗黑' }}
          </button>
          <!-- 移动端导航收起/展开 -->
          <button class="menu-btn" @click="showMenu = !showMenu" v-if="isMobile">
            ☰
          </button>
          <ul class="nav-menu" :class="{ show: showMenu }">
            <li><a href="#hero">首页</a></li>
            <li><a href="#skills">技能栈</a></li>
            <li><a href="#projects">项目经历</a></li>
            <li><a href="#contact">联系方式</a></li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- 2. Hero区（核心个人信息） -->
    <section id="hero" class="hero">
      <div class="container">
        <div class="hero-content">
          <h2>你好，我是 <span class="highlight">XXX</span></h2>
          <h3>专注于 Vue 技术栈的前端开发工程师</h3>
          <p class="hero-desc">
            擅长响应式布局、组件化开发，熟悉前端工程化流程，
            追求优雅的代码和良好的用户体验，期待加入靠谱的团队共同成长。
          </p>
          <div class="hero-btns">
            <a href="#contact" class="btn primary-btn">联系我</a>
            <a href="https://github.com/你的GitHub账号" target="_blank" class="btn secondary-btn">GitHub</a>
          </div>
        </div>
        <!-- 可选：加一张简约的个人头像/前端相关插画 -->
        <div class="hero-img">
          <img src="https://picsum.photos/300/300" alt="个人头像" />
        </div>
      </div>
    </section>

    <!-- 3. 技能栈（分维度展示） -->
    <section id="skills" class="skills">
      <div class="container">
        <h2 class="section-title">我的技能栈</h2>
        <div class="skills-grid">
          <!-- 核心技术 -->
          <div class="skill-card">
            <h3>核心前端</h3>
            <ul>
              <li>HTML5/CSS3：语义化标签、Flex/Grid、响应式适配</li>
              <li>JavaScript：ES6+、DOM操作、异步编程(Promise/async-await)</li>
              <li>Vue3：Composition API、Pinia、Vue Router、Teleport</li>
            </ul>
          </div>
          <!-- 工具/框架 -->
          <div class="skill-card">
            <h3>工具/框架</h3>
            <ul>
              <li>工程化：Vite、Webpack、npm/yarn、ESLint</li>
              <li>UI框架：Element Plus、Vant、TailwindCSS</li>
              <li>其他：Git、Axios、Postman、Chrome调试</li>
            </ul>
          </div>
          <!-- 了解/学习中 -->
          <div class="skill-card">
            <h3>了解/学习中</h3>
            <ul>
              <li>TypeScript：基础类型、接口、泛型</li>
              <li>小程序：微信小程序基础开发</li>
              <li>可视化：ECharts基础使用</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- 4. 项目经历（核心，对应你的作品集） -->
    <section id="projects" class="projects">
      <div class="container">
        <h2 class="section-title">项目经历</h2>
        <!-- 项目1：个人简历主页 -->
        <div class="project-item">
          <div class="project-header">
            <h3>Vue3 响应式个人简历主页</h3>
            <span class="project-tag">Vue3 + Vite + CSS3</span>
          </div>
          <p class="project-desc">
            核心功能：多端响应式适配（PC/平板/手机）、暗黑模式切换、页面平滑滚动、导航锚点定位
          </p>
          <p class="project-highlight">
            技术亮点：使用CSS变量实现主题切换，基于IntersectionObserver实现滚动动画，媒体查询适配多端布局
          </p>
          <div class="project-links">
            <a href="你的在线预览链接" target="_blank" class="link-btn">在线预览</a>
            <a href="你的GitHub代码链接" target="_blank" class="link-btn">查看代码</a>
          </div>
        </div>
        <!-- 项目2：Vue3后台管理系统 -->
        <div class="project-item">
          <div class="project-header">
            <h3>Vue3 + Element Plus 后台管理系统</h3>
            <span class="project-tag">Vue3 + Element Plus + Pinia + Vue Router</span>
          </div>
          <p class="project-desc">
            核心功能：登录鉴权&路由守卫、用户管理（增删改查）、表格分页/搜索/批量操作、表单验证
          </p>
          <p class="project-highlight">
            技术亮点：基于Pinia管理用户状态，封装通用表格/表单组件，路由懒加载优化性能
          </p>
          <div class="project-links">
            <a href="你的在线预览链接" target="_blank" class="link-btn">在线预览</a>
            <a href="你的GitHub代码链接" target="_blank" class="link-btn">查看代码</a>
          </div>
        </div>
        <!-- 项目3：待办清单 -->
        <div class="project-item">
          <div class="project-header">
            <h3>Vue3 本地待办清单</h3>
            <span class="project-tag">Vue3 + localStorage + 组件化</span>
          </div>
          <p class="project-desc">
            核心功能：待办事项增删改查、完成状态切换、本地数据持久化、空值校验
          </p>
          <p class="project-highlight">
            技术亮点：封装TodoItem组件，基于localStorage实现数据缓存，响应式处理列表渲染
          </p>
          <div class="project-links">
            <a href="你的在线预览链接" target="_blank" class="link-btn">在线预览</a>
            <a href="你的GitHub代码链接" target="_blank" class="link-btn">查看代码</a>
          </div>
        </div>
      </div>
    </section>

    <!-- 5. 工作/实习经历（可选，没有就删掉） -->
    <section id="experience" class="experience" v-if="hasExperience">
      <div class="container">
        <h2 class="section-title">工作/实习经历</h2>
        <div class="exp-item">
          <div class="exp-header">
            <h3>前端开发实习生</h3>
            <span>XX公司 | 202X.X - 202X.X</span>
          </div>
          <ul class="exp-desc">
            <li>参与公司官网的响应式改版，使用Vue3实现页面组件化开发</li>
            <li>协助优化移动端页面加载速度，减少白屏时间约30%</li>
            <li>使用Element Plus实现后台管理系统的表单和表格模块</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- 6. 教育背景 -->
    <section id="education" class="education">
      <div class="container">
        <h2 class="section-title">教育背景</h2>
        <div class="edu-item">
          <h3>XX大学 - 计算机科学与技术（专科/本科）</h3>
          <span>202X.X - 202X.X | 学历：XX</span>
          <p>相关课程：JavaScript、HTML/CSS、计算机网络（可选）</p>
        </div>
      </div>
    </section>

    <!-- 7. 联系方式 -->
    <section id="contact" class="contact">
      <div class="container">
        <h2 class="section-title">联系方式</h2>
        <div class="contact-grid">
          <div class="contact-item">
            <span class="contact-icon">📱</span>
            <p>手机号：13XXXXXXXXX</p>
          </div>
          <div class="contact-item">
            <span class="contact-icon">📧</span>
            <p>邮箱：xxx@xxx.com</p>
          </div>
          <div class="contact-item">
            <span class="contact-icon">💻</span>
            <p>GitHub：<a href="https://github.com/你的账号" target="_blank">github.com/你的账号</a></p>
          </div>
          <div class="contact-item">
            <span class="contact-icon">📍</span>
            <p>求职地点：XX城市</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 8. 页脚 -->
    <footer class="footer">
      <div class="container">
        <p>© 2026 XXX（你的名字）- 前端开发工程师 | 基于Vue3开发</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, watch } from 'vue'

// 暗黑模式
const isDark = ref(false)
// 移动端菜单显示/隐藏
const showMenu = ref(false)
// 是否有工作/实习经历（没有就改成false）
const hasExperience = ref(true)
// 是否为移动端
const isMobile = ref(window.innerWidth < 768)

// 监听窗口大小变化
const handleResize = () => {
  isMobile.value = window.innerWidth < 768
  // 移动端窗口变化时收起菜单
  if (isMobile.value) showMenu.value = false
}

// 初始化
onMounted(() => {
  // 监听系统暗黑模式
  if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
    isDark.value = true
  }
  // 监听窗口大小
  window.addEventListener('resize', handleResize)
  // 平滑滚动
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      e.preventDefault()
      const targetId = this.getAttribute('href')
      document.querySelector(targetId).scrollIntoView({
        behavior: 'smooth'
      })
      // 点击导航后收起移动端菜单
      showMenu.value = false
    })
  })
})

// 监听暗黑模式变化，同步到localStorage（加分）
watch(isDark, (newVal) => {
  localStorage.setItem('darkMode', newVal)
})
</script>

<style scoped>
/* 全局样式重置 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
  text-decoration: none;
}

/* 基础变量 */
:root {
  --primary-color: #42b983; /* Vue绿，贴合技术栈 */
  --bg-color: #ffffff;
  --text-color: #333333;
  --card-bg: #f8f9fa;
  --border-color: #e9ecef;
  --hover-color: #e6f7ef;
}

/* 暗黑模式变量 */
.dark {
  --bg-color: #1a1a1a;
  --text-color: #e5e5e5;
  --card-bg: #2d2d2d;
  --border-color: #444444;
  --hover-color: #383838;
}

/* 基础样式 */
.app {
  min-height: 100vh;
  background: var(--bg-color);
  color: var(--text-color);
  transition: all 0.3s ease;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-title {
  font-size: 28px;
  margin-bottom: 40px;
  text-align: center;
  position: relative;
}

.section-title::after {
  content: '';
  display: block;
  width: 80px;
  height: 3px;
  background: var(--primary-color);
  margin: 10px auto;
}

/* 导航样式 */
.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: var(--bg-color);
  border-bottom: 1px solid var(--border-color);
  padding: 15px 0;
  z-index: 999;
}

.nav .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-left {
  display: flex;
  align-items: center;
  gap: 10px;
}

.nav-subtitle {
  font-size: 14px;
  color: #888;
}

.nav-menu {
  display: flex;
  gap: 20px;
}

.nav-menu a {
  color: var(--text-color);
  padding: 5px 10px;
  border-radius: 4px;
  transition: background 0.3s;
}

.nav-menu a:hover {
  background: var(--hover-color);
  color: var(--primary-color);
}

.theme-btn {
  background: var(--primary-color);
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 4px;
  cursor: pointer;
  margin-right: 15px;
}

.menu-btn {
  display: none;
  background: none;
  border: none;
  font-size: 20px;
  color: var(--text-color);
  cursor: pointer;
}

/* Hero区 */
.hero {
  padding: 120px 0 80px;
  background: var(--card-bg);
  margin-top: 60px;
}

.hero .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
}

.hero-content {
  flex: 1;
}

.hero h2 {
  font-size: 36px;
  margin-bottom: 10px;
}

.hero h3 {
  font-size: 24px;
  color: #666;
  margin-bottom: 20px;
}

.highlight {
  color: var(--primary-color);
}

.hero-desc {
  font-size: 16px;
  line-height: 1.6;
  margin-bottom: 30px;
  color: #777;
}

.hero-btns {
  display: flex;
  gap: 15px;
}

.btn {
  padding: 10px 20px;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
  transition: all 0.3s;
}

.primary-btn {
  background: var(--primary-color);
  color: white;
  border: none;
}

.secondary-btn {
  background: transparent;
  color: var(--primary-color);
  border: 1px solid var(--primary-color);
}

.hero-img img {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  object-fit: cover;
  border: 5px solid var(--primary-color);
}

/* 技能栈 */
.skills {
  padding: 80px 0;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.skill-card {
  background: var(--card-bg);
  padding: 25px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
}

.skill-card h3 {
  color: var(--primary-color);
  margin-bottom: 15px;
  font-size: 20px;
}

.skill-card li {
  margin-bottom: 8px;
  line-height: 1.5;
}

/* 项目经历 */
.projects {
  padding: 80px 0;
  background: var(--card-bg);
}

.project-item {
  background: var(--bg-color);
  padding: 30px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
  margin-bottom: 30px;
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.project-tag {
  background: var(--primary-color);
  color: white;
  padding: 5px 10px;
  border-radius: 4px;
  font-size: 14px;
}

.project-desc {
  line-height: 1.6;
  margin-bottom: 10px;
}

.project-highlight {
  color: var(--primary-color);
  line-height: 1.6;
  margin-bottom: 15px;
}

.project-links {
  display: flex;
  gap: 10px;
}

.link-btn {
  color: var(--primary-color);
  font-size: 14px;
  text-decoration: underline;
}

/* 工作/实习经历 */
.experience {
  padding: 80px 0;
}

.exp-item {
  background: var(--card-bg);
  padding: 30px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
}

.exp-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
}

.exp-header h3 {
  color: var(--primary-color);
}

.exp-desc li {
  margin-bottom: 10px;
  line-height: 1.6;
  list-style: disc;
  margin-left: 20px;
}

/* 教育背景 */
.education {
  padding: 80px 0;
  background: var(--card-bg);
}

.edu-item {
  background: var(--bg-color);
  padding: 30px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
}

.edu-item h3 {
  margin-bottom: 10px;
}

.edu-item span {
  color: #888;
  margin-bottom: 15px;
  display: block;
}

/* 联系方式 */
.contact {
  padding: 80px 0;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  text-align: center;
}

.contact-item {
  background: var(--card-bg);
  padding: 25px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
}

.contact-icon {
  font-size: 24px;
  margin-bottom: 10px;
  display: block;
}

.contact-item a {
  color: var(--primary-color);
}

/* 页脚 */
.footer {
  padding: 30px 0;
  background: var(--card-bg);
  text-align: center;
  border-top: 1px solid var(--border-color);
}

/* 响应式适配 */
@media (max-width: 768px) {
  .menu-btn {
    display: block;
  }

  .nav-menu {
    position: fixed;
    top: 70px;
    left: 0;
    width: 100%;
    background: var(--bg-color);
    flex-direction: column;
    padding: 20px;
    border-bottom: 1px solid var(--border-color);
    transform: translateY(-200%);
    transition: transform 0.3s;
  }

  .nav-menu.show {
    transform: translateY(0);
  }

  .hero .container {
    flex-direction: column;
    text-align: center;
  }

  .hero-btns {
    justify-content: center;
  }

  .hero-img {
    margin-top: 30px;
  }

  .section-title {
    font-size: 24px;
  }

  .hero h2 {
    font-size: 28px;
  }

  .hero h3 {
    font-size: 20px;
  }

  .project-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
  }
}
</style>