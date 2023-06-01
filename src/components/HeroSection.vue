<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    created(){
        this.setAnimation()
    },
    methods:{
        setAnimation(){
            console.log('Hello');
            window.addEventListener('scroll', function() {
                if(window.pageYOffset == 330){
                    console.log(window.pageYOffset)
                    //@ts-ignore
                    gsap.fromTo(".box", {x: -120, opacity: 0.1}, {x: 0, opacity: 1, duration: 1});
                    //@ts-ignore
                    gsap.fromTo(".goto", {x: 120, opacity: 0.1}, {x: 0, opacity: 1, duration: 1});
                }else return null
            });
        }
    }
})
</script>

<template>
    <div class="pl-[100px] pr-[0px] space-x-[40px] w-full flex pt-[146px]">
        <div class="w-[40%]">
            <div class="font-[800] text-[#414263] text-[130px] leading-[120px]">BARMERRE SODOR
                <span class="text-[#fff] text-[140px] leading-[140px]">A SZEL</span>
            </div>
            <div class="w-[40%] mt-[-40px] h-[60px] bg-[#fff] layerBlur"></div>
            <div class="pt-[156px] w-[90%] box h-fit font-[700] text-[#1A1B3A] text-[40px] leading-[52px]">
                Mi segítünk, hogy mindenhol
                otthon érezd magad!
            </div>
            <div class="rounded-[10px] box cursor-pointer text-[20px] leading-[20px] text-[#252649] font-[700] mt-[46px] text-center w-[300px] py-[26px] border border-[#252649]">
                Csatlakozz hozzánk!
            </div>
        </div>
        <!--second flex-->
        <div class="w-[60%]">
            <div class="flex mt-[188px] w-full">
                <div class="w-[30%]"></div>
                <div class="w-[70%] h-fit flex sideflex">
                    <div class="w-[50%] pt-[38px]">
                        <div class="flex space-x-[32px] pr-[36px] items-center">
                            <div class="w-[10px] bg-[#80DD47] h-[40px]"></div>
                            <div class="text-[20px] text-[#252649] leading-[20px] font-[600]">Friss ajánlatok</div>
                        </div>
                        <div class="mt-[34px] pl-[42px] pr-[36px]">
                            <div class="font-[700] text-[#252649] leading-[48.6px] text-[36px]">Új-Zéland</div>
                            <div class="font-[600] mt-[10px] text-[#252649] leading-[24.3px] text-[18px]">Távol és mégis közel. A legjobb 10 hotel Új-Zélandon.</div>
                            <div class="mt-[67px] text-[#252649] leading-[18.9px] text-[14px] font-[400] mb-[43px]">
                                <div>#adventure</div>
                                <div>#mountains</div>
                                <div>#dolapo lol</div>
                            </div>
                        </div>
                    </div>
                    <div class="w-[50%]">
                        <img src="/Image/img.png" class="w-full h-full" alt=""/>
                    </div>
                </div>
            </div>
            <!--goto blabala-->
            <div class="flex goto space-x-[12px] mt-[57px] w-[70%]">
                <div class="w-[70%]">
                    <div class="text-[#252649] mb-[7px] leading-[27px] text-[20px] font-[700]">Gyorsabban, olcsóbban!</div>
                    <div class="font-[500] text-[#252649] text-[14px] leading-[18.9px]">Iratkozz fel hírlevelünkre, és a legjobb ajánlatokban részesülhetsz!</div>
                </div>
                <div><img src="/Image/button.svg" class="cursor-pointer" alt=""/></div>
            </div>
            <!--end goto blablabla-->
        </div>
        <!--end second flex-->
    </div>
</template>

<style scoped>
.layerBlur{
    filter: blur(21.5px)
}
.sideflex{
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(35px);
    border-radius: 16px 0px 0px 16px;
}
</style>