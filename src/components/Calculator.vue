<template>
<div> 
    <div class="container">
        <Header></Header>

        <div> 
            <PermissionItem :data-item="ownerData" @changeCheckBox="handleChangeCheckBox"> </PermissionItem>
            <PermissionItem :data-item="groupData" @changeCheckBox="handleChangeCheckBox"> </PermissionItem>
            <PermissionItem :data-item="publicData" @changeCheckBox="handleChangeCheckBox"> </PermissionItem>
        </div>

        <PermissionMoniter :data-monitor="dataMonitor"></PermissionMoniter>
    </div>
</div>
  
</template>

<script>
import Header from "@/components/Header";
import PermissionItem from "@/components/PermissionItem";
import PermissionMonitor from "@/components/PermissionMonitor";

export default {
    name: 'Caculator',
    components: {
        Header,
        PermissionItem,
        PermissionMonitor
    },
    data: function () {
        return {
            ownerData:{
                id: 0,
                type: 'Owner',
                bit: '000'
            },
            groupData:{
                id: 1,
                type: 'Group',
                bit: '000'
            },
            publicData:{
                id: 2,
                type: 'Public',
                bit: '000'
            }
        }
       
    },
    methods: {
        bitToNumber(bit){
            return (parseInt(bit[0])*4 + parseInt(bit[1])*2 + parseInt(bit[2])).toString();
        },

        bitToSymbol(bit){
            let tmp = '';
            tmp += bit[0] === '1' ? 'r' : '-';
            tmp += bit[1] === '1' ? 'w' : '-';
            tmp += bit[2] === '1' ? 'x' : '-';
            return tmp;
        },

        handleChangeCheckBox: function (itemBit, itemId) {
            (itemId === 0) ? this.ownerData.bit = itemBit : (itemId === 1) ? 
            this.groupData.bit = itemBit : this.publicData.bit = itemBit;
        }

        

        
    },
    computed:{
        numValue: function () {
            return bitToNumber(this.ownerData.bit) + bitToNumber(this.groupData.bit) + bitToNumber(this.publicData.bit);
        },

        symValue: function () {
            return bitToSymbol(this.ownerData.bit) + bitToSymbol(this.groupData.bit) + bitToSymbol(this.publicData.bit);
        },
        dataMonitor: function(){
            return {
                numValue : this.numValue,
                symValue : this.symValue
            }
        }
    }
    

}
</script scoped>

<style>

</style>