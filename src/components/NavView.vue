<script setup lang="ts">
import { ref } from 'vue'
const submitForm=(e:any)=>{
    e.preventDefault()
}

//||input data reference
const fullname = ref('')
const email = ref('')
const phoneNumber = ref('')
const date = ref('')
const bookModal = ref(false)
const oneBorder = ref(false)
const twoBorder = ref(false)
const threeBorder = ref(false)
const price = ref()
const vat = ref()
const total = ref()
const verified = ref(false)
const bookingSpace = ref(true)


//functions
const openBookModal=()=>{
    bookModal.value = true;
    bookingSpace.value = true;
}
const closeModal=(e:any)=>{
    if(e.target.matches('.bookingBg')){
        bookModal.value = false;
        verified.value = false;
        fullname.value = '';
        email.value = '';
        phoneNumber.value = '';
        date.value = '';
        oneBorder.value = false;
        twoBorder.value = false;
        threeBorder.value = false;
        price.value = '';
        vat.value = '';
        total.value = '';
    } else bookModal.value = true
}
const firstImage=()=>{
    oneBorder.value = true;
    twoBorder.value = false;
    threeBorder.value = false;
    const priceList = 20000;
    const vats = 5000;
    price.value = `Price is: N${priceList.toLocaleString()}`;
    vat.value = `VAT: N${vats.toLocaleString()}`;
    const grand = priceList + vats
    total.value = `Total: N${grand.toLocaleString()}`
}
const secondImage=()=>{
    oneBorder.value = false;
    twoBorder.value = true;
    threeBorder.value = false;
    const priceList = 50000;
    const vats = 8000;
    price.value = `Price is: N${priceList.toLocaleString()}`;
    vat.value = `VAT: N${vats.toLocaleString()}`;
    const grand = priceList + vats
    total.value = `Total: N${grand.toLocaleString()}`
}
const thirdImage=()=>{
    oneBorder.value = false;
    twoBorder.value = false;
    threeBorder.value = true;
    const priceList = 15000;
    const vats = 6000;
    price.value = `Price is: N${priceList.toLocaleString()}`;
    vat.value = `VAT: N${vats.toLocaleString()}`;
    const grand = priceList + vats
    total.value = `Total: N${grand.toLocaleString()}`
}
const verifyBooking=()=>{
    if((!fullname.value) || (!email.value) || (!phoneNumber.value) || (!date.value)){
        verified.value = false;
        bookingSpace.value = true;
    }else{
        verified.value = true;
        bookingSpace.value = false;
    }
}
</script>

<template>
    <div>
        <div class="px-[100px]">
            <div class="pt-[32px] pb-[25px] flex items-center justify-between">
                <div><img src="/Image/passengerLogo.svg" class="" alt=""/></div>
                <div class="flex items-center font-[400] text-[#fff] leading-[21.48px] text-[18px] space-x-[50px]">
                    <div class="cursor-pointer">Uti celok</div>
                    <div class="cursor-pointer">Szallasok</div>
                    <div class="cursor-pointer">Magazin</div>
                    <div @click="openBookModal" class="cursor-pointer">Book</div>
                </div>
            </div>
            <div class="border border-[#fff]"></div>
        </div>
        <!--booking form-->
        <div @click="closeModal" v-show="bookModal" class="bookingBg z-[100] overflow-y-scroll w-full top-0 fixed h-full">
            <div v-show="bookingSpace" class="bg-[#fff] px-[77px] py-[30px] mb-[201px] h-fit mx-auto mt-[100px] w-[80%] rounded-[10px]">
                <form @submit="submitForm">
                    <div class="flex mb-[56px] space-x-[102px] w-full">
                        <div class="w-[45%]">
                            <div class="font-[700] mb-[19px] text-[#333333] leading-[24.2px] text-[17px]"><label for="name">Full Name</label></div>
                            <input v-model="fullname" id="name" autocomplete="off" type="text" placeholder="Enter your full name" class="w-full rounded-[4px] text-[14px] bg-[#F1F1F1] px-[16px] py-[16px] focus:outline-none placeholder:text-[#666666]"/>
                        </div>
                        <div class="w-[45%]">
                            <div class="font-[700] mb-[19px] text-[#333333] leading-[24.2px] text-[17px]"><label for="email">Email</label></div>
                            <input v-model="email" id="email" autocomplete="off" type="email" placeholder="Enter your email" class="w-full rounded-[4px] text-[14px] bg-[#F1F1F1] px-[16px] py-[16px] focus:outline-none placeholder:text-[#666666]"/>
                        </div>
                    </div>
                    <!---->
                    <div class="flex mb-[41px] space-x-[102px] w-full">
                        <div class="w-[45%]">
                            <div class="font-[700] mb-[19px] text-[#333333] leading-[24.2px] text-[17px]"><label for="number">Phone Number</label></div>
                            <input v-model="phoneNumber" id="number" autocomplete="off" type="text" placeholder="Enter your phone number" class="w-full rounded-[4px] text-[14px] bg-[#F1F1F1] px-[16px] py-[16px] focus:outline-none placeholder:text-[#666666]"/>
                        </div>
                        <div class="w-[45%]">
                            <div class="font-[700] mb-[19px] text-[#333333] leading-[24.2px] text-[17px]"><label for="date">Date</label></div>
                            <input v-model="date" id="date" autocomplete="off" type="date" class="w-full rounded-[4px] text-[14px] bg-[#F1F1F1] px-[16px] py-[16px] focus:outline-none placeholder:text-[#666666]"/>
                        </div>
                    </div>
                    <!---->
                    <div class="flex mb-[41px] space-x-[102px] w-full">
                        <div class="w-[45%] flex space-x-[30px]">
                            <div @click="firstImage" :class="oneBorder ? 'border-[3px] rounded-[4px] border-[#000]': 'border-[0px] rounded-[0px]'" class="w-[30%] hotelone cursor-pointer bg-[#DED6D6] h-[77px]"></div>
                            <div @click="secondImage" :class="twoBorder ? 'border-[3px] rounded-[4px] border-[#000]': 'border-[0px] rounded-[0px]'" class="w-[30%] hoteltwo cursor-pointer bg-[#DED6D6] h-[77px]"></div>
                            <div @click="thirdImage" :class="threeBorder ? 'border-[3px] rounded-[4px] border-[#000]': 'border-[0px] rounded-[0px]'" class="w-[30%] hotelthree cursor-pointer bg-[#DED6D6] h-[77px]"></div>
                        </div>
                        <div class="w-[45%]">
                            <div class="rounded-[4px] w-full border border-[#000]">
                                <div>
                                    <div>{{price}}</div>
                                    <div>{{vat}}</div>
                                    <div>{{total}}</div>
                                </div>
                                <div @click="verifyBooking" class="bg-[#0180C7] cursor-pointer w-full text-center font-[700] text-[#fff] leading-[24.2px] text-[20px] py-[16px] rounded-b-[4px] mt-[30px]">
                                    Book now
                                </div>
                            </div>
                        </div>
                    </div>
                    <!---->
                </form>
            </div>
            <div v-show="verified" class="bg-[#fff] mt-[100px] rounded-[4px] mx-auto w-[35%] py-[20px] px-[20px]">
                <img src="/Image/badge.svg" class="mx-auto" alt=""/>
                <div class="mx-auto font-[700] text-[20px] text-center mt-[10px]">{{fullname}}</div>
                <div class="mx-auto w-[60%] font-[400] mt-[3px] text-[15px] text-center">
                    You have successfully booked a room from Passenger.
                </div>
            </div>
        </div>
        <!--end booking form-->
    </div>
</template>

<style scoped>
.bookingBg{
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(35px);
}
.bookingBg::-webkit-scrollbar{
    display: none;
}
.hotelone{
    background: url('/Image/hotelone.png');
    background-repeat: no-repeat;
    background-size: 100%;
    background-position: contain;
}
.hoteltwo{
    background: url('/Image/hoteltwo.png');
    background-repeat: no-repeat;
    background-size: 100%;
    background-position: contain;
}
.hotelthree{
    background: url('/Image/hotelthree.png');
    background-repeat: no-repeat;
    background-size: 100%;
    background-position: contain;
}
</style>