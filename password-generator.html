<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>安全密码生成器</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
            color: #333;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 30px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        input[type="range"] {
            width: 100%;
        }
        .checkbox-group {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }
        .checkbox-item {
            display: flex;
            align-items: center;
        }
        .checkbox-item input {
            margin-right: 8px;
        }
        .result-container {
            display: flex;
            margin-top: 20px;
        }
        #password-result {
            flex-grow: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
            font-size: 16px;
            background-color: #f9f9f9;
        }
        #copy-btn {
            padding: 10px 15px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        #copy-btn:hover {
            background-color: #2980b9;
        }
        #generate-btn {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #2ecc71;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
            margin-top: 20px;
        }
        #generate-btn:hover {
            background-color: #27ae60;
        }
        .strength-meter {
            height: 5px;
            background-color: #eee;
            margin-top: 10px;
            border-radius: 5px;
            overflow: hidden;
        }
        .strength-bar {
            height: 100%;
            width: 0%;
            transition: width 0.3s, background-color 0.3s;
        }
        .length-display {
            text-align: center;
            font-weight: bold;
            margin-top: 5px;
        }
        .copied-message {
            color: #2ecc71;
            text-align: center;
            margin-top: 10px;
            opacity: 0;
            transition: opacity 0.3s;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>安全密码生成器</h1>
        
        <div class="form-group">
            <label for="password-length">密码长度: <span id="length-value">12</span></label>
            <input type="range" id="password-length" min="4" max="32" value="12">
            <div class="strength-meter">
                <div class="strength-bar" id="strength-bar"></div>
            </div>
        </div>
        
        <div class="form-group">
            <label>包含字符类型:</label>
            <div class="checkbox-group">
                <div class="checkbox-item">
                    <input type="checkbox" id="lowercase" checked>
                    <label for="lowercase">小写字母 (a-z)</label>
                </div>
                <div class="checkbox-item">
                    <input type="checkbox" id="uppercase" checked>
                    <label for="uppercase">大写字母 (A-Z)</label>
                </div>
                <div class="checkbox-item">
                    <input type="checkbox" id="numbers" checked>
                    <label for="numbers">数字 (0-9)</label>
                </div>
                <div class="checkbox-item">
                    <input type="checkbox" id="symbols" checked>
                    <label for="symbols">符号 (!@#$%^&*)</label>
                </div>
            </div>
        </div>
        
        <div class="form-group">
            <label for="password-result">生成的密码:</label>
            <div class="result-container">
                <input type="text" id="password-result" readonly>
                <button id="copy-btn">复制</button>
            </div>
            <div class="copied-message" id="copied-message">密码已复制!</div>
        </div>
        
        <button id="generate-btn">生成密码</button>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const lengthSlider = document.getElementById('password-length');
            const lengthValue = document.getElementById('length-value');
            const lowercaseCheckbox = document.getElementById('lowercase');
            const uppercaseCheckbox = document.getElementById('uppercase');
            const numbersCheckbox = document.getElementById('numbers');
            const symbolsCheckbox = document.getElementById('symbols');
            const passwordResult = document.getElementById('password-result');
            const generateBtn = document.getElementById('generate-btn');
            const copyBtn = document.getElementById('copy-btn');
            const copiedMessage = document.getElementById('copied-message');
            const strengthBar = document.getElementById('strength-bar');
            
            // 更新密码长度显示
            lengthSlider.addEventListener('input', function() {
                lengthValue.textContent = this.value;
                updateStrengthMeter();
            });
            
            // 字符类型复选框变化时更新强度计
            [lowercaseCheckbox, uppercaseCheckbox, numbersCheckbox, symbolsCheckbox].forEach(checkbox => {
                checkbox.addEventListener('change', updateStrengthMeter);
            });
            
            // 生成密码
            generateBtn.addEventListener('click', generatePassword);
            
            // 复制密码
            copyBtn.addEventListener('click', function() {
                if (passwordResult.value) {
                    passwordResult.select();
                    document.execCommand('copy');
                    
                    // 显示复制成功消息
                    copiedMessage.style.opacity = '1';
                    setTimeout(() => {
                        copiedMessage.style.opacity = '0';
                    }, 2000);
                }
            });
            
            // 初始生成一个密码
            generatePassword();
            
            function generatePassword() {
                const length = parseInt(lengthSlider.value);
                const includeLower = lowercaseCheckbox.checked;
                const includeUpper = uppercaseCheckbox.checked;
                const includeNumbers = numbersCheckbox.checked;
                const includeSymbols = symbolsCheckbox.checked;
                
                // 验证至少选择了一种字符类型
                if (!includeLower && !includeUpper && !includeNumbers && !includeSymbols) {
                    alert('请至少选择一种字符类型!');
                    return;
                }
                
                // 定义字符集
                let charset = '';
                if (includeLower) charset += 'abcdefghijklmnopqrstuvwxyz';
                if (includeUpper) charset += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
                if (includeNumbers) charset += '0123456789';
                if (includeSymbols) charset += '!@#$%^&*()_+-=[]{}|;:,.<>?';
                
                // 生成密码
                let password = '';
                for (let i = 0; i < length; i++) {
                    const randomIndex = Math.floor(Math.random() * charset.length);
                    password += charset[randomIndex];
                }
                
                passwordResult.value = password;
                updateStrengthMeter();
            }
            
            function updateStrengthMeter() {
                const length = parseInt(lengthSlider.value);
                const includeLower = lowercaseCheckbox.checked;
                const includeUpper = uppercaseCheckbox.checked;
                const includeNumbers = numbersCheckbox.checked;
                const includeSymbols = symbolsCheckbox.checked;
                
                // 计算密码强度
                let strength = 0;
                
                // 长度加分
                if (length >= 8) strength += 1;
                if (length >= 12) strength += 1;
                if (length >= 16) strength += 1;
                
                // 字符类型多样性加分
                let charTypes = 0;
                if (includeLower) charTypes++;
                if (includeUpper) charTypes++;
                if (includeNumbers) charTypes++;
                if (includeSymbols) charTypes++;
                
                if (charTypes >= 2) strength += 1;
                if (charTypes >= 3) strength += 1;
                if (charTypes >= 4) strength += 1;
                
                // 更新强度条
                let width = 0;
                let color = '#e74c3c'; // 红色
                
                if (strength <= 2) {
                    width = 33;
                    color = '#e74c3c'; // 红色
                } else if (strength <= 4) {
                    width = 66;
                    color = '#f39c12'; // 橙色
                } else {
                    width = 100;
                    color = '#2ecc71'; // 绿色
                }
                
                strengthBar.style.width = width + '%';
                strengthBar.style.backgroundColor = color;
            }
        });
    </script>
</body>
</html>
