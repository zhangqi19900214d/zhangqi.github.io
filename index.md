---
layout: default
---

<body>
  <script src="/js/fire-boom.js"></script>

  <script>
    const cursorSpecialEffects = new CursorSpecialEffects()
    cursorSpecialEffects.init()
  </script>

  <div class="index-wrapper">
    <div class="aside">
      <div class="info-card">
          <div id="divcss5"><img src="/images/header.png" /></div>
          <br/><br/>
          <div align="left" id="index_tag">
            <script src="/js/dynamic-scrollbarl.js"></script>
            <ul class="categories-list">
              {% for cat in site.categories %}
                {% assign categories = categories | append: cat[0] | append: "__zhqi__" %}
              {% endfor %}
              {% assign categories = categories | append: "myleetcode" | append: "__zhqi__" %}


              {% assign categories = categories | split: "__zhqi__" | sort %}

              {% for category in categories %}
                {% for cat in site.categories %}
                  {% capture show_tag %}{{cat[0]}}{% endcapture %}
                  {% if show_tag == category %}
                    {% if show_tag == "data_struct" %}
                       <a href="数据结构" class="title"> 数据结构 </a>
                    {% elsif show_tag == "raspberrypi" %}
                       <a href="树莓派" class="title"> 树莓派实验室 </a>
                    {% elsif show_tag == "network" %}
                       <a href="计算机网络" class="title"> 计算机网络 </a>
                    {% elsif show_tag == "Distributed-OS" %}
                       <a href="分布式系统" class="title"> 分布式系统 </a>
                    {% elsif show_tag == "CPP" %}
                       <a href="C++" class="title"> C++ </a>
                    {% elsif show_tag == "cv" %}
                       <a href="图像识别" class="title"> 图像识别 </a>
                    {% elsif show_tag == "recommend" %}
                       <a href="推荐系统" class="title"> 推荐系统 </a>
                    {% elsif show_tag == "others" %}
                       <a href="知识盲区" class="title"> 知识盲区 </a>
                    {% else %}
                       <a href="{{ show_tag }}" class="title"> {{ show_tag }} </a>
                    {% endif %}
                    <br/>
                    {% break %}
                  {% endif %}
                {% endfor %}
              {% endfor %}
            </ul>
          </div>
          <br/>
          <div class="new-article">
            <a href="https://blog.csdn.net/zhangqi_gsts">
            <img src="https://raw.githubusercontent.com/meiqizhang/zhangqi.github.io/master/images/csdn.ico" style="border-radius:50%; width: 32px">
            </a>
  
            <a href="https://github.com/meiqizhang">
              <img src="https://github.githubassets.com/favicon.ico" style="border-radius:50%; width: 32px">
            </a>
          </div>
        </div>
      <div id="particles-js">
      </div>
    </div>
    <!-- 正文 -->
    <div class="index-content">
      <ul class="artical-list">
        {% for post in site.posts %}
            <li>
              <a href="{{ post.url }}" class="title">{{ post.title }}</a>
              <div class="title-desc">{{ post.description }}</div>
            </li>
        {% endfor %}
      </ul>
    </div>
    
    <div class="right-info-card">
        <div>
            <iframe name="" frameborder="0" scrolling="no" marginwidth="0" marginheight="0" width="100%" height="250" src="/calendar.html"></iframe> 
        </div>
        <!--
        <div class="new-article" align="center">
            <br><br>
            <h3>最新文章</h3>
            {% for cat in site.categories %}
                {% for post in cat[1] %}
                    <li>
                    <a href="{{ post.url }}">{{ post.title }}</a>
                    </li>
                {% endfor %}
            {% endfor %}
         </div>
         -->
         
     </div>
      
      
  </div>
</body>
