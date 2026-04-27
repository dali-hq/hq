<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>一月初健康餐盒訂購系統</title>
    <style>
        :root {
            --orange: #FF9800;
            --pink: #E91E63;
            --red: #D32F2F;
        }
        body { font-family: "Microsoft JhengHei", sans-serif; background: #f8f9fa; margin: 0; padding: 20px; }
        .container { max-width: 900px; margin: auto; }
        
        /* 菜單圖片區 */
        .menu-banner { text-align: center; margin-bottom: 20px; }
        .menu-banner img { width: 100%; max-width: 400px; border-radius: 10px; cursor: pointer; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }

        .section-title { padding: 12px; color: white; border-radius: 5px; margin-top: 25px; font-weight: bold; }
        .bg-orange { background-color: var(--orange); }
        .bg-pink { background-color: var(--pink); }
        .bg-red { background-color: var(--red); }

        .menu-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: 12px; margin-top: 15px; }
        .menu-item { background: white; padding: 20px; border-radius: 8px; border-left: 5px solid transparent; box-shadow: 0 2px 5px rgba(0,0,0,0.05); cursor: pointer; text-align: center; font-weight: bold; transition: 0.2s; }
        .menu-item:hover { transform: scale(1.03); background: #fffcf9; }

        /* Modal 彈窗優化 */
        .modal { display: none; position: fixed; z-index: 100; left: 0; top: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); }
        .modal-content { background: white; width: 90%; max-width: 450px; margin: 8% auto; padding: 25px; border-radius: 12px; }
        
        .form-group { margin-bottom: 20px; }
        label { display: block; margin-bottom: 8px; font-weight: bold; color: #444; }
        input[type="text"], select, textarea { width: 100%; padding: 10px; box-sizing: border-box; border: 1px solid #ccc; border-radius: 6px; font-size: 16px; }

        /* 飯量圓圈選取樣式 */
        .rice-options { display: flex; flex-wrap: wrap; gap: 10px; }
        .rice-options label { 
            display: flex; align-items: center; background: #eee; padding: 8px 15px; border-radius: 20px; 
            cursor: pointer; font-weight: normal; font-size: 14px; transition: 0.2s;
        }
        .rice-options input[type="radio"] { margin-right: 8px; width: 18px; height: 18px; cursor: pointer; }
        .rice-options label:hover { background: #e0e0e0; }
        input[type="radio"]:checked + span { font-weight: bold; color: #D32F2F; }

        .btn-submit { width: 100%; padding: 12px; background: #28a745; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 18px; font-weight: bold; }
        .btn-cancel { width: 100%; margin-top: 10px; background: none; color: #888; border: none; cursor: pointer; text-decoration: underline; }
    </style>
</head>
<body>

<div class="container">
    <div class="menu-banner">
        <a href="https://lh3.googleusercontent.com/d/1AvmLPM6kOiekJaOLIHFI8txWShy8blIN" target="_blank">
            <img src="https://lh3.googleusercontent.com/d/1AvmLPM6kOiekJaOLIHFI8txWShy8blIN" alt="點擊查看菜單大圖">
        </a>
        <p style="font-size: 12px; color: #666;">(點擊圖片可開新視窗查看大圖)</p>
    </div>

    <div class="section-title bg-orange">活力輕享</div>
    <div class="menu-grid" id="light-share" style="border-top: 3px solid var(--orange);"></div>

    <div class="section-title bg-pink">清爽元氣</div>
    <div class="menu-grid" id="fresh-energy" style="border-top: 3px solid var(--pink);"></div>

    <div class="section-title bg-red">特色盒餐</div>
    <div class="menu-grid" id="special-box" style="border-top: 3px solid var(--red);"></div>
</div>

<div id="orderModal" class="modal">
    <div class="modal-content">
        <h2 id="selectedItemName" style="margin-top:0; color:var(--red);">品項名稱</h2>
        <form id="orderForm">
            <input type="hidden" id="menuItem">
            
            <div class="form-group">
                <label>訂購人姓名</label>
                <input type="text" id="userName" required>
            </div>

            <div id="flavorGroup" class="form-group" style="display:none;">
                <label>口味選擇</label>
                <select id="flavorSelection"></select>
            </div>

            <div class="form-group">
                <label>飯量選擇 (必選)</label>
                <div class="rice-options">
                    <label><input type="radio" name="rice" value="紫米" required><span>紫米</span></label>
                    <label><input type="radio" name="rice" value="白飯"><span>白飯</span></label>
                    <label><input type="radio" name="rice" value="紅藜麥飯"><span>紅藜麥飯</span></label>
                    <label><input type="radio" name="rice" value="飯少(8分)"><span>飯少(8分)</span></label>
                    <label><input type="radio" name="rice" value="飯一半"><span>飯一半</span></label>
                </div>
            </div>

            <div class="form-group">
                <label>備註</label>
                <textarea id="note" rows="2"></textarea>
            </div>

            <button type="submit" class="btn-submit">確認送出訂單</button>
            <button type="button" onclick="closeModal()" class="btn-cancel">取消返回</button>
        </form>
    </div>
</div>

<script>
    const menuData = {
        light: ["塔香三杯雞", "蒜泥白肉豬", "黑胡椒清蒸鯛魚", "季節食蔬(素)"],
        fresh: ["舒肥雞塔可飯", "鯛魚塔可飯", "培根蝦塔可飯", "舒肥雞堅果沙拉", "鮮蝦堅果沙拉"],
        special: [
            { name: "舒肥嫩煮雞", flavors: ["原味", "蜜汁烤肉醬", "鹹蛋黃塔塔", "椒鹽檸檬", "港式蔥鹽", "蒜香蜂蜜"] },
            { name: "日式唐揚雞", flavors: ["椒鹽", "松露醬", "桂花釀"] },
            "泰式椒麻雞", "宮保雞丁", "薑汁燒肉豬", "香烤松阪豬", "日式照燒牛", "川辣口水牛(辣)", "蔥爆牛柳(辣)", "照燒金磚魚", "清蒸鱸魚", "舒肥嫩鮭魚"
        ]
    };

    function renderMenu() {
        const render = (containerId, items) => {
            const container = document.getElementById(containerId);
            items.forEach(item => {
                const div = document.createElement('div');
                div.className = 'menu-item';
                const name = typeof item === 'string' ? item : item.name;
                div.innerText = name;
                div.onclick = () => openModal(item);
                container.appendChild(div);
            });
        };
        render('light-share', menuData.light);
        render('fresh-energy', menuData.fresh);
        render('special-box', menuData.special);
    }

    function openModal(item) {
        const isObject = typeof item === 'object';
        const name = isObject ? item.name : item;
        document.getElementById('selectedItemName').innerText = name;
        document.getElementById('menuItem').value = name;
        
        const flavorGroup = document.getElementById('flavorGroup');
        const flavorSelect = document.getElementById('flavorSelection');
        if (isObject && item.flavors) {
            flavorGroup.style.display = 'block';
            flavorSelect.innerHTML = item.flavors.map(f => `<option value="${f}">${f}</option>`).join('');
        } else {
            flavorGroup.style.display = 'none';
            flavorSelect.innerHTML = '';
        }
        
        document.getElementById('orderModal').style.display = 'block';
    }

    function closeModal() { document.getElementById('orderModal').style.display = 'none'; }

    document.getElementById('orderForm').onsubmit = function(e) {
        e.preventDefault();
        const riceVal = document.querySelector('input[name="rice"]:checked').value;
        const data = {
            name: document.getElementById('userName').value,
            item: document.getElementById('menuItem').value,
            flavor: document.getElementById('flavorSelection').value || '原味/無',
            rice: riceVal,
            note: document.getElementById('note').value
        };

        const GAS_URL = "https://script.google.com/macros/s/AKfycbzkuKwCUf-9VLdkvqP53QE6DLp6LOngncKZaVgwNrphT4iQWTs6q2jm_2MOtEMk2QId/exec"; 
        
        fetch(GAS_URL, {
            method: "POST",
            mode: "no-cors",
            body: JSON.stringify(data)
        }).then(() => {
            alert("訂單已送出！感謝訂購。");
            closeModal();
            this.reset();
        }).catch(err => alert("傳送失敗，請聯繫管理員。"));
    };

    renderMenu();
</script>
</body>
</html>
