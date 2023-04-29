<script>
// 点击量饼图数据
const clickLabel = ["哔哩哔哩(大号 播放量)", "哔哩哔哩(大号 阅读量)", "哔哩哔哩(小号 播放量)", "哔哩哔哩(小号 阅读量)", "知乎", "CSDN", "VSMarketplace"];
const clickData = [250246, 52624, 192162, 49937, 122226, 184753, 43500];

// 点击量求和
var clickAll = 0;
for (let i = 0; i < clickData.length; i++) {
    clickAll += clickData[i];
}

// 粉丝量饼图数据
const followerLabel = ["哔哩哔哩(大号)", "哔哩哔哩(小号)", "知乎", "CSDN"];
const followerData = [1300, 468, 57, 208];

// 点击量求和
var followerAll = 0;
for (let i = 0; i < followerData.length; i++) {
    followerAll += followerData[i];
}

// 饼图背景色
const doughnutBackgroundColor = ["rgba(255, 99, 132)", "rgba(255, 159, 64)", "rgba(255, 205, 86)", "rgba(75, 192, 192)", "rgba(54, 162, 235)", "rgba(153, 102, 255)", "rgba(201, 203, 207)"]
</script>

<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.4.0/Chart.min.js"></script>

<style>
.left {
    float: left;
    width: 50%;
}

.right {
    float: right;
    width: 50%;
}
</style>

<div class="left">
    <canvas id="clickgraph" width="3" height="2"></canvas>
    <script>
        var ctx = document.getElementById('clickgraph').getContext('2d');
        var chart = new Chart(ctx, {
            // 要创建的图表类型
            type: 'doughnut',

            // 数据集
            data: {
                labels: clickLabel,
                datasets: [{
                    backgroundColor: doughnutBackgroundColor,
                    data: clickData,
                }]
            },

            // 配置选项
            options: {
                title: {
                    display: true,
                    text: "各平台点击量分布（个）"
                }
            }
        });
    </script>
</div>
<div class="right">
    <canvas id="followergraph" width="3" height="2"></canvas>
    <script>
        var ctx = document.getElementById('followergraph').getContext('2d');
        var chart = new Chart(ctx, {
            // 要创建的图表类型
            type: 'doughnut',

            // 数据集
            data: {
                labels: followerLabel,
                datasets: [{
                    backgroundColor: doughnutBackgroundColor,
                    data: followerData,
                }]
            },

            // 配置选项
            options: {
                title: {
                    display: true,
                    text: "各平台粉丝量分布（个）"
                }
            }
        });
    </script>
</div>
