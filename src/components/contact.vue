/**
* Created by WangMing on 15/12/9.
*/
<style>
.contact-panel{
    background-color: #F44336;
    color: white;
    position: absolute;
    bottom: 0;
    right: 0;
    top: 57px;
    left: 150px;
}
</style>

<template>
    <table class="pure-table pure-table-horizontal">
        <thead>
            <tr>
                <th @click="doSomething">#</th>
                <th>Make</th>
                <th>Model</th>
                <th>Year</th>
            </tr>
        </thead>

        <tbody>
            <tr v-for="item in items">
                <td>{{ $index }}</td>
                <td>{{ item.message }}</td>
                <td>{{ parentMessage }}</td>
                <td>{{ item.message2 }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>
    module.exports = {
        data: function () {
            return {
                parentMessage: 'Parent',
                items: [
                  { message: 'Foo', message2: 'Foo2',},
                  { message: 'Bar', message2: 'Bar2' }
                ]
            }
        },
        methods: {
          doSomething: function (e) {
            console.log(this.data);
          },
          doData: function (data) {
            console.log(data);
          }
        }
    };
</script>
