    <template>
  <div style="  display:flex;flex-wrap:nowrap;justify-content:flex-end;height:30px;width:100vw;">
    <div id="titlebar">
      <div style="display:flex;justify-content:center;align-items:center;width:50px;height:100%;">
        <img id="logo"
             src="~@/assets/logo.png"
             alt="electron-vue"
             height="70%">
      </div>
      <div id="menu"></div>
      <div id="title"
           style="display:flex;flex-wrap:nowrap;justify-content:center;align-items:center;">
        <div> Terminally []</div>
      </div>
    </div>
    <div style="display:flex;justify-content:flex-end;align-items:center;width:auto;height:100%">
      <div :id="minactive"
           @click="min()"
           @mouseover="minactive='mouseOver'"
           @mouseleave="minactive='mouseLeave'">
        <div style="width:40px;height:40%;display:flex;justify-content:center;align-items:center;">
          <img src="~@/assets/min.png"
               alt="min"
               height="100%">
        </div>
      </div>
      <div :id="maxactive"
           v-on:click="max()"
           @mouseover="maxactive='mouseOver'"
           @mouseleave="maxactive='mouseLeave'">
        <div style="width:40px;height:40%;display:flex;justify-content:center;align-items:center;">
          <img src="~@/assets/max.png"
               alt="max"
               height="100%">
        </div>
      </div>
      <div :id="closeactive ?'CLOSEmouseOver':'CLOSEmouseLeave'"
           v-on:click="close()"
           @mouseover="closeactive=1"
           @mouseleave="closeactive=0">
        <div style="width:40px;height:40%;display:flex;justify-content:center;align-items:center;">
          <img :src="closeactive ? closeonUrl : closeoffUrl"
               alt="close"
               height="100%">
        </div>
      </div>
    </div>
  </div>
</template>