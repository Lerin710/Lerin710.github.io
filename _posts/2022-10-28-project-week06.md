--- 
jupyter:
  colab:
  kernelspec:
    display_name: Python 3
    name: python3
  language_info:
    name: python
  nbformat: 4
  nbformat_minor: 0
---

::: {.cell .code execution_count="1" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="cBMhT6EiE6Lp" outputId="ccf24c66-f93b-4b17-fc12-d0df0fc61302"}
``` {.python}
# 한글 폰트 처리 : 런타임 다시 시작 필요
!sudo apt-get install -y fonts-nanum
!sudo fc-cache -fv
!rm ~/.cache/matplotlib -rf
```

::: {.output .stream .stdout}
    Reading package lists... Done
    Building dependency tree       
    Reading state information... Done
    The following package was automatically installed and is no longer required:
      libnvidia-common-460
    Use 'sudo apt autoremove' to remove it.
    The following NEW packages will be installed:
      fonts-nanum
    0 upgraded, 1 newly installed, 0 to remove and 27 not upgraded.
    Need to get 9,604 kB of archives.
    After this operation, 29.5 MB of additional disk space will be used.
    Get:1 http://archive.ubuntu.com/ubuntu bionic/universe amd64 fonts-nanum all 20170925-1 [9,604 kB]
    Fetched 9,604 kB in 1s (8,020 kB/s)
    debconf: unable to initialize frontend: Dialog
    debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 76, <> line 1.)
    debconf: falling back to frontend: Readline
    debconf: unable to initialize frontend: Readline
    debconf: (This frontend requires a controlling tty.)
    debconf: falling back to frontend: Teletype
    dpkg-preconfigure: unable to re-open stdin: 
    Selecting previously unselected package fonts-nanum.
    (Reading database ... 123942 files and directories currently installed.)
    Preparing to unpack .../fonts-nanum_20170925-1_all.deb ...
    Unpacking fonts-nanum (20170925-1) ...
    Setting up fonts-nanum (20170925-1) ...
    Processing triggers for fontconfig (2.12.6-0ubuntu2) ...
    /usr/share/fonts: caching, new cache contents: 0 fonts, 1 dirs
    /usr/share/fonts/truetype: caching, new cache contents: 0 fonts, 3 dirs
    /usr/share/fonts/truetype/humor-sans: caching, new cache contents: 1 fonts, 0 dirs
    /usr/share/fonts/truetype/liberation: caching, new cache contents: 16 fonts, 0 dirs
    /usr/share/fonts/truetype/nanum: caching, new cache contents: 10 fonts, 0 dirs
    /usr/local/share/fonts: caching, new cache contents: 0 fonts, 0 dirs
    /root/.local/share/fonts: skipping, no such directory
    /root/.fonts: skipping, no such directory
    /var/cache/fontconfig: cleaning cache directory
    /root/.cache/fontconfig: not cleaning non-existent cache directory
    /root/.fontconfig: not cleaning non-existent cache directory
    fc-cache: succeeded
:::
:::

::: {.cell .code execution_count="2" id="ro_1z9DHFVuj"}
``` {.python}
import matplotlib as mpl
import matplotlib.pyplot as plt
import numpy as np

%matplotlib inline
```
:::

::: {.cell .code execution_count="3" id="Lmj-QfH2FfRg"}
``` {.python}
# matplotlib 한글폰트 지정
plt.rc('font', family='NanumBarunGothic')

# - 기호 깨짐 오류 방지
plt.rc('axes', unicode_minus = False)
```
:::

::: {.cell .code execution_count="5" colab="{\"height\":265,\"base_uri\":\"https://localhost:8080/\"}" id="EeAxZKgWFhow" outputId="17789699-8806-4cb6-e91f-c6ce0f22a448"}
``` {.python}
# x측
x = ['1월', '2월', '3월', '4월', '5월']
y = [7, 10, 17, 20, 23]

# 그래프
plt.plot(x,y)
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/483d505de8737872c6f0af4ee45a391e5c7b6469.png)
:::
:::

::: {.cell .code execution_count="6" colab="{\"height\":283,\"base_uri\":\"https://localhost:8080/\"}" id="glknLB7tFjFk" outputId="5ce6b0da-9157-4c13-dce8-482101794a7c"}
``` {.python}
# x측
x = ['1월', '2월', '3월', '4월', '5월']
y = [7, 10, 17, 20, 23]

# 그래프
plt.plot(x,y, color="blue", marker = 'o', linestyle = ':')
plt.title('월별 평균 온도', fontsize=15)
plt.ylabel('온도(도)')
plt.grid(linestyle = ':')
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/a4b9343ed1434af92be5a6c9156033881710c9bb.png)
:::
:::

::: {.cell .code execution_count="7" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="2b8cC6kTFvMh" outputId="04c8b9ba-c6bf-470a-ed66-ef731d03ed79"}
``` {.python}
# 40개의 임의의 랜덤값을 생성
aVal = np.random.standard_normal(40)
aVal
```

::: {.output .execute_result execution_count="7"}
    array([ 0.47928923,  0.67437096, -0.2007285 ,  0.01532397, -0.69579718,
           -0.16124468,  0.24943922,  1.28796772,  0.10010696, -0.15757577,
           -0.37102544, -1.00494577, -0.69107072, -0.02341633, -0.10253284,
           -0.23397794,  1.5063563 , -0.82988308,  0.02211996, -0.52805603,
           -0.06169195, -0.12256423, -1.30941485,  1.94268748,  0.29986136,
            1.1759208 ,  0.89940336, -0.4030054 , -2.09363397, -0.74437782,
           -1.2576965 ,  1.09442298, -0.40358724, -0.11836022, -0.95220776,
            0.27294792, -0.07865213, -1.74670381,  1.51766088,  1.08483112])
:::
:::

::: {.cell .code execution_count="8" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="6zgs2VRJFxSQ" outputId="3b1ab366-473c-44a1-e4c8-1c17fd659538"}
``` {.python}
# type 확인
# 40개의 랜덤값으로 이루어진 numpy.ndarray형 변수
type(aVal)
```

::: {.output .execute_result execution_count="8"}
    numpy.ndarray
:::
:::

::: {.cell .code execution_count="9" colab="{\"height\":265,\"base_uri\":\"https://localhost:8080/\"}" id="KEIlpxb6Fzsc" outputId="a36019b9-5ae9-49f2-d82d-ea1495620829"}
``` {.python}
index = range(len(aVal))
plt.plot(index, aVal)

# x축, y축의 범위 설정
plt.xlim(0, 20)
plt.ylim(np.min(aVal) -1, np.max(aVal) + 1)
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/8f3f91f1e3723f1fea18b8c48020cc99b9b633c8.png)
:::
:::

::: {.cell .code execution_count="10" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="fp-Ef4tpF0gP" outputId="a7f57091-7e52-4682-ec26-b11143b741d0"}
``` {.python}
# index는 range 형 변수
type(index)
```

::: {.output .execute_result execution_count="10"}
    range
:::
:::

::: {.cell .code execution_count="11" colab="{\"height\":313,\"base_uri\":\"https://localhost:8080/\"}" id="89nfr9G4F2ik" outputId="111a14ef-07ec-40ea-cf47-f407fa448d35"}
``` {.python}
plt.figure(figsize=(7,4))
plt.plot(aVal.cumsum(), 'b', lw= 1.5)
plt.plot(aVal.cumsum(), 'ro')
plt.xlabel('index')
plt.ylabel('aVal')
plt.title('Line Plot')
plt.show()
```

::: {.output .stream .stderr}
    WARNING:matplotlib.font_manager:findfont: Font family ['NanumBarunGothic'] not found. Falling back to DejaVu Sans.
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/b0b345e30471e9d72bae7a640483eb5a81de81f2.png)
:::
:::

::: {.cell .code execution_count="12" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="-8-eMnEmF5_R" outputId="07a95c2b-11bb-4856-c7aa-6109e8765191"}
``` {.python}
value = np.random.standard_normal((30, 2))
value
```

::: {.output .execute_result execution_count="12"}
    array([[-0.98012483, -0.57307398],
           [-2.43910787, -2.55807383],
           [ 1.31305112,  0.97862637],
           [-0.29450509,  0.40360965],
           [-0.03255552,  0.36477126],
           [-1.28864041,  0.56803839],
           [ 0.34272407, -1.34091691],
           [ 0.00966518, -0.23105579],
           [ 0.23841609, -0.31855236],
           [-1.58669798,  0.86786284],
           [-0.63937583, -0.29758332],
           [ 1.4327974 , -0.72421804],
           [ 0.01163296,  0.4760898 ],
           [-2.02665534, -0.05043444],
           [-0.66218112,  2.50232909],
           [-0.86383271, -0.49789961],
           [ 0.55867558, -0.09524537],
           [ 0.13871403, -0.62258593],
           [ 1.45669397,  0.98898512],
           [-0.42307238,  0.07593851],
           [ 0.7323979 ,  0.58101665],
           [ 2.30301297, -0.63214383],
           [-0.16762009, -0.0689363 ],
           [-0.76116382, -2.20462686],
           [ 1.69074367,  0.45582965],
           [ 0.69943362, -1.05301991],
           [-1.21960455, -0.51869641],
           [ 0.02097268, -0.61907868],
           [ 0.35587253, -2.45927551],
           [ 1.18072249,  0.53234258]])
:::
:::

::: {.cell .code execution_count="13" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="cQwQHnt_F8WU" outputId="e1d1fc11-85b0-4ba5-c2a7-c444807d64dd"}
``` {.python}
value[0]
```

::: {.output .execute_result execution_count="13"}
    array([-0.98012483, -0.57307398])
:::
:::

::: {.cell .code execution_count="14" colab="{\"height\":313,\"base_uri\":\"https://localhost:8080/\"}" id="OtrKbVWcF-EH" outputId="873d648e-d501-4631-cbad-dea9c86826bf"}
``` {.python}
plt.figure(figsize=(10,4))
plt.plot(value[:,0], lw= 1.5)
plt.plot(value[:,1], lw= 1.5)
plt.plot(value, 'ro')
plt.grid(True)
# plt.legend(loc=0)
plt.xlabel('index')
plt.ylabel('value')
plt.title('Line Plot')
```

::: {.output .execute_result execution_count="14"}
    Text(0.5, 1.0, 'Line Plot')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/9b9eef395ca1e447c58d138521cafbb08c4a3db6.png)
:::
:::

::: {.cell .code execution_count="15" colab="{\"height\":354,\"base_uri\":\"https://localhost:8080/\"}" id="aysMwhFvF_rp" outputId="40f13214-d9bc-4306-97ef-eef9e036d7a6"}
``` {.python}
# 1번째
plt.figure(figsize=(10,5))
plt.subplot(211)
plt.plot(value[:,0], lw = 1.5, label = '1st')
plt.plot(value[:,0], 'ro')
plt.grid(True)
plt.legend(loc = 0)
plt.ylabel("value")
plt.title('Line Plot 3')
# 2번째
plt.subplot(212)
plt.plot(value[:,1], 'g', lw = 1.5, label = '2nd')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
```

::: {.output .execute_result execution_count="15"}
    Text(0, 0.5, 'value')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/7bf9b7aade85a4b5f8f42831aa549a4fcc0dbc2b.png)
:::
:::

::: {.cell .code execution_count="16" colab="{\"height\":354,\"base_uri\":\"https://localhost:8080/\"}" id="QY0zsW7CGHuL" outputId="de40a971-42d3-4603-df08-519fa8900ee2"}
``` {.python}
# 1번째
plt.figure(figsize=(13,5))
plt.subplot(231)
plt.plot(value[:,0], lw= 1.5, label = '1st')
plt.plot(value[:,0], 'co')
plt.grid(True)
plt.legend(loc=0)
plt.ylabel('value')
plt.title('Line Plot 3')
# 2번째
plt.subplot(232)
plt.plot(value[:,0], 'g-.', lw=1.5, label='1st')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
# 3번째
plt.subplot(233)
plt.plot(value[:,0], 'g', lw=1.5, label='1st')
plt.plot(value[:,0], 'bD')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
# 4번째
plt.subplot(234)
plt.plot(value[:,1], '*', lw=1.5, label='2nd')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
# 5번째
plt.subplot(235)
plt.plot(value[:,1], 'b', lw=1.5, label='2nd')
plt.plot(value[:,1], 'ms')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
# 6번째
plt.subplot(236)
plt.plot(value[:,1], 'r--', lw=1.5, label='2nd')
plt.grid(True)
plt.legend(loc=0)
plt.axis('tight')
plt.ylabel('value')
```

::: {.output .execute_result execution_count="16"}
    Text(0, 0.5, 'value')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/1ec69baebd7f8fd324d1374ee7cbf2ad9d0e21c3.png)
:::
:::

::: {.cell .code execution_count="17" colab="{\"height\":358,\"base_uri\":\"https://localhost:8080/\"}" id="5tX0SW_6GLrL" outputId="f1defe53-cb6e-41a4-b6ac-38a1c3ea80ad"}
``` {.python}
# x측
x = ['1월', '2월', '3월', '4월', '5월']
y = [7, 10, 17, 20, 23]

# 그래프
plt.bar(x,y)
plt.show()
```

::: {.output .stream .stderr}
    /usr/local/lib/python3.7/dist-packages/matplotlib/backends/backend_agg.py:214: RuntimeWarning: Glyph 50900 missing from current font.
      font.set_text(s, 0.0, flags=flags)
    /usr/local/lib/python3.7/dist-packages/matplotlib/backends/backend_agg.py:183: RuntimeWarning: Glyph 50900 missing from current font.
      font.set_text(s, 0, flags=flags)
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/32652802b738cc43b1ae6b7cbe753083781b5554.png)
:::
:::

::: {.cell .code execution_count="18" colab="{\"height\":265,\"base_uri\":\"https://localhost:8080/\"}" id="ZV7Rei_EGN29" outputId="4798d8a0-413d-4d46-fc0a-4fc2f044c88f"}
``` {.python}
# x측
x = ['1월', '2월', '3월', '4월', '5월']
y = [7, 10, 17, 20, 23]

# 그래프
plt.barh(x,y)
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/e898a9ba9d6aa9f9841a4015381ae7290d9ff50c.png)
:::
:::

::: {.cell .code execution_count="20" colab="{\"height\":283,\"base_uri\":\"https://localhost:8080/\"}" id="Hh-OpqHXGQBH" outputId="083efdc7-f4ca-4c1c-e388-27d6a80d8aee"}
``` {.python}
# x측
x = ['1월', '2월', '3월', '4월', '5월']
y = [7, 10, 17, 20, 23]

# 그래프
plt.bar(x,y, color="orange", width = 0.5, edgecolor = 'black', hatch = '/')
plt.title('월별 평균 온도', fontsize=15)
plt.ylabel('온도(도)')
plt.grid(linestyle = ':', axis = 'y')
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/fc734a26a6b6ca62eb5bc4e25713f6bcca885374.png)
:::
:::

::: {.cell .code execution_count="30" colab="{\"height\":77,\"base_uri\":\"https://localhost:8080/\"}" id="UPt7jUR0GUjY" outputId="7c3620d2-0f4f-496f-cb6d-890cfa0fcba8"}
``` {.python}
#파일 직접 업로드하기
from google.colab import files
myfile = files.upload()
```

::: {.output .display_data}
```{=html}
     <input type="file" id="files-b2c12028-f4a7-4254-b3ee-f413488a8398" name="files[]" multiple disabled
        style="border:none" />
     <output id="result-b2c12028-f4a7-4254-b3ee-f413488a8398">
      Upload widget is only available when the cell has been executed in the
      current browser session. Please rerun this cell to enable.
      </output>
      <script>// Copyright 2017 Google LLC
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//      http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

/**
 * @fileoverview Helpers for google.colab Python module.
 */
(function(scope) {
function span(text, styleAttributes = {}) {
  const element = document.createElement('span');
  element.textContent = text;
  for (const key of Object.keys(styleAttributes)) {
    element.style[key] = styleAttributes[key];
  }
  return element;
}

// Max number of bytes which will be uploaded at a time.
const MAX_PAYLOAD_SIZE = 100 * 1024;

function _uploadFiles(inputId, outputId) {
  const steps = uploadFilesStep(inputId, outputId);
  const outputElement = document.getElementById(outputId);
  // Cache steps on the outputElement to make it available for the next call
  // to uploadFilesContinue from Python.
  outputElement.steps = steps;

  return _uploadFilesContinue(outputId);
}

// This is roughly an async generator (not supported in the browser yet),
// where there are multiple asynchronous steps and the Python side is going
// to poll for completion of each step.
// This uses a Promise to block the python side on completion of each step,
// then passes the result of the previous step as the input to the next step.
function _uploadFilesContinue(outputId) {
  const outputElement = document.getElementById(outputId);
  const steps = outputElement.steps;

  const next = steps.next(outputElement.lastPromiseValue);
  return Promise.resolve(next.value.promise).then((value) => {
    // Cache the last promise value to make it available to the next
    // step of the generator.
    outputElement.lastPromiseValue = value;
    return next.value.response;
  });
}

/**
 * Generator function which is called between each async step of the upload
 * process.
 * @param {string} inputId Element ID of the input file picker element.
 * @param {string} outputId Element ID of the output display.
 * @return {!Iterable<!Object>} Iterable of next steps.
 */
function* uploadFilesStep(inputId, outputId) {
  const inputElement = document.getElementById(inputId);
  inputElement.disabled = false;

  const outputElement = document.getElementById(outputId);
  outputElement.innerHTML = '';

  const pickedPromise = new Promise((resolve) => {
    inputElement.addEventListener('change', (e) => {
      resolve(e.target.files);
    });
  });

  const cancel = document.createElement('button');
  inputElement.parentElement.appendChild(cancel);
  cancel.textContent = 'Cancel upload';
  const cancelPromise = new Promise((resolve) => {
    cancel.onclick = () => {
      resolve(null);
    };
  });

  // Wait for the user to pick the files.
  const files = yield {
    promise: Promise.race([pickedPromise, cancelPromise]),
    response: {
      action: 'starting',
    }
  };

  cancel.remove();

  // Disable the input element since further picks are not allowed.
  inputElement.disabled = true;

  if (!files) {
    return {
      response: {
        action: 'complete',
      }
    };
  }

  for (const file of files) {
    const li = document.createElement('li');
    li.append(span(file.name, {fontWeight: 'bold'}));
    li.append(span(
        `(${file.type || 'n/a'}) - ${file.size} bytes, ` +
        `last modified: ${
            file.lastModifiedDate ? file.lastModifiedDate.toLocaleDateString() :
                                    'n/a'} - `));
    const percent = span('0% done');
    li.appendChild(percent);

    outputElement.appendChild(li);

    const fileDataPromise = new Promise((resolve) => {
      const reader = new FileReader();
      reader.onload = (e) => {
        resolve(e.target.result);
      };
      reader.readAsArrayBuffer(file);
    });
    // Wait for the data to be ready.
    let fileData = yield {
      promise: fileDataPromise,
      response: {
        action: 'continue',
      }
    };

    // Use a chunked sending to avoid message size limits. See b/62115660.
    let position = 0;
    do {
      const length = Math.min(fileData.byteLength - position, MAX_PAYLOAD_SIZE);
      const chunk = new Uint8Array(fileData, position, length);
      position += length;

      const base64 = btoa(String.fromCharCode.apply(null, chunk));
      yield {
        response: {
          action: 'append',
          file: file.name,
          data: base64,
        },
      };

      let percentDone = fileData.byteLength === 0 ?
          100 :
          Math.round((position / fileData.byteLength) * 100);
      percent.textContent = `${percentDone}% done`;

    } while (position < fileData.byteLength);
  }

  // All done.
  yield {
    response: {
      action: 'complete',
    }
  };
}

scope.google = scope.google || {};
scope.google.colab = scope.google.colab || {};
scope.google.colab._files = {
  _uploadFiles,
  _uploadFilesContinue,
};
})(self);
</script> 
```
:::

::: {.output .stream .stdout}
    Saving scores.csv to scores.csv
:::
:::

::: {.cell .code execution_count="31" id="M8ptmZsDIzKT"}
``` {.python}
#io와 pandas 모듈 import
import io
import pandas as pd
```
:::

::: {.cell .code execution_count="36" colab="{\"height\":363,\"base_uri\":\"https://localhost:8080/\"}" id="dAtMYFrhI0Ak" outputId="43e94b21-9c5e-4560-9973-29b939b4371c"}
``` {.python}
# score.csv 파일 일기
df = pd.read_csv('scores.csv', encoding='cp949')
df
```

::: {.output .execute_result execution_count="36"}
```{=html}
  <div id="df-409c7e5e-c8c0-47cd-ba93-b592cfe74c62">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-409c7e5e-c8c0-47cd-ba93-b592cfe74c62')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-409c7e5e-c8c0-47cd-ba93-b592cfe74c62 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-409c7e5e-c8c0-47cd-ba93-b592cfe74c62');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
```
:::
:::

::: {.cell .code execution_count="37" colab="{\"height\":265,\"base_uri\":\"https://localhost:8080/\"}" id="WQSyrNDPJd3f" outputId="977d8f99-76e1-41c7-8457-af00b0d5e422"}
``` {.python}
x = df['이름']
y_kor = df['국어']

plt.bar(x, y_kor)
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/b5617ad506d6eff9a959abe05b757c3808cf3a94.png)
:::
:::

::: {.cell .code execution_count="39" colab="{\"height\":283,\"base_uri\":\"https://localhost:8080/\"}" id="hiNx_N8GJgkx" outputId="0da61303-dfa2-4033-a7d7-ca3b7055bea5"}
``` {.python}
x = df['이름']
y_kor = df['국어']
y_eng = df['영어']

# 중심을 기준으로 왼쪽/오른쪽에 그래프를 구성
plt.bar(x, y_kor, width = -0.4, align = 'edge', label = '국어')
plt.bar(x, y_eng, width = 0.4, align = 'edge', label = '영어')
plt.title('국어/영어 점수 비교', fontsize = 15)
plt.ylabel('점수')

# 범례
plt.legend() 
plt.show()
```

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/c0d1715b298d190a744ff82e869552eb29e89f60.png)
:::
:::

::: {.cell .code execution_count="40" colab="{\"height\":313,\"base_uri\":\"https://localhost:8080/\"}" id="MWiJEAdZJkMx" outputId="7545fac0-970a-478e-e093-d40e55d648a0"}
``` {.python}
value = np.random.standard_normal((500,2))
plt.plot(value[:,0], value[:,1], 'ro')
plt.grid(False)
plt.xlabel('value 1')
plt.ylabel('value 2')
plt.title('Scatter Plot 1')
```

::: {.output .execute_result execution_count="40"}
    Text(0.5, 1.0, 'Scatter Plot 1')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/64d88a1d8f3d0347c68ce9b2828aba7e0e7d7f2a.png)
:::
:::

::: {.cell .code execution_count="41" colab="{\"height\":368,\"base_uri\":\"https://localhost:8080/\"}" id="Bzl4Gd60JmEq" outputId="f4966861-fe76-4a88-89cc-5768d00af27d"}
``` {.python}
plt.figure(figsize=(7,5))
plt.scatter(value[:,0], value[:,1], marker='o')
plt.grid(True)
plt.xlabel('value 1')
plt.ylabel('value 2')
plt.title('Scatter Plot 2')
```

::: {.output .execute_result execution_count="41"}
    Text(0.5, 1.0, 'Scatter Plot 2')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/7638e99ab265e117455a5f37bd03e43ee6b07ea2.png)
:::
:::

::: {.cell .code execution_count="42" colab="{\"height\":368,\"base_uri\":\"https://localhost:8080/\"}" id="gE7dtDH7JoL4" outputId="b02edcf4-16d2-4f30-d650-97a6e35004f2"}
``` {.python}
color = np.random.randint(0,10,len(value))

plt.figure(figsize=(10,5))
plt.scatter(value[:,0], value[:,1], c=color, marker = 'o')
plt.colorbar()
plt.xlabel('value 1')
plt.ylabel('value 2')
plt.title('Scatter Plot 3')
```

::: {.output .execute_result execution_count="42"}
    Text(0.5, 1.0, 'Scatter Plot 3')
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/121e64707047be31053c41e8a34d2dba93fde773.png)
:::
:::

::: {.cell .code execution_count="43" colab="{\"height\":424,\"base_uri\":\"https://localhost:8080/\"}" id="J4Qm77AOJprw" outputId="85c0335e-b059-44a5-fe2e-29f8345f40ed"}
``` {.python}
import seaborn as sns
df = sns.load_dataset('tips')
df
```

::: {.output .execute_result execution_count="43"}
```{=html}
  <div id="df-ea04da4c-8ed9-4acc-b8e5-9bc830c4cefc">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_bill</th>
      <th>tip</th>
      <th>sex</th>
      <th>smoker</th>
      <th>day</th>
      <th>time</th>
      <th>size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>16.99</td>
      <td>1.01</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10.34</td>
      <td>1.66</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>21.01</td>
      <td>3.50</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>23.68</td>
      <td>3.31</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>24.59</td>
      <td>3.61</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>239</th>
      <td>29.03</td>
      <td>5.92</td>
      <td>Male</td>
      <td>No</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>240</th>
      <td>27.18</td>
      <td>2.00</td>
      <td>Female</td>
      <td>Yes</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>241</th>
      <td>22.67</td>
      <td>2.00</td>
      <td>Male</td>
      <td>Yes</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>242</th>
      <td>17.82</td>
      <td>1.75</td>
      <td>Male</td>
      <td>No</td>
      <td>Sat</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>243</th>
      <td>18.78</td>
      <td>3.00</td>
      <td>Female</td>
      <td>No</td>
      <td>Thur</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>244 rows × 7 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-ea04da4c-8ed9-4acc-b8e5-9bc830c4cefc')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-ea04da4c-8ed9-4acc-b8e5-9bc830c4cefc button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-ea04da4c-8ed9-4acc-b8e5-9bc830c4cefc');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
```
:::
:::

::: {.cell .code execution_count="44" colab="{\"height\":206,\"base_uri\":\"https://localhost:8080/\"}" id="3jDE4WRoJrAU" outputId="cbc90ace-2096-4539-9a05-6b574e148098"}
``` {.python}
df.head()
```

::: {.output .execute_result execution_count="44"}
```{=html}
  <div id="df-1030e5e3-3930-4c06-9918-67314f2f092d">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_bill</th>
      <th>tip</th>
      <th>sex</th>
      <th>smoker</th>
      <th>day</th>
      <th>time</th>
      <th>size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>16.99</td>
      <td>1.01</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10.34</td>
      <td>1.66</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>21.01</td>
      <td>3.50</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>23.68</td>
      <td>3.31</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>24.59</td>
      <td>3.61</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1030e5e3-3930-4c06-9918-67314f2f092d')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1030e5e3-3930-4c06-9918-67314f2f092d button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1030e5e3-3930-4c06-9918-67314f2f092d');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
```
:::
:::

::: {.cell .code execution_count="45" colab="{\"height\":300,\"base_uri\":\"https://localhost:8080/\"}" id="hTAEMuAKJtc2" outputId="63e28e3b-64a6-4b92-8792-842555f19f48"}
``` {.python}
df.describe()
```

::: {.output .execute_result execution_count="45"}
```{=html}
  <div id="df-877a3048-6fc8-4ab7-90d2-b1226a66b81a">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_bill</th>
      <th>tip</th>
      <th>size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>244.000000</td>
      <td>244.000000</td>
      <td>244.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>19.785943</td>
      <td>2.998279</td>
      <td>2.569672</td>
    </tr>
    <tr>
      <th>std</th>
      <td>8.902412</td>
      <td>1.383638</td>
      <td>0.951100</td>
    </tr>
    <tr>
      <th>min</th>
      <td>3.070000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>13.347500</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>17.795000</td>
      <td>2.900000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>24.127500</td>
      <td>3.562500</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>50.810000</td>
      <td>10.000000</td>
      <td>6.000000</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-877a3048-6fc8-4ab7-90d2-b1226a66b81a')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-877a3048-6fc8-4ab7-90d2-b1226a66b81a button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-877a3048-6fc8-4ab7-90d2-b1226a66b81a');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
```
:::
:::

::: {.cell .code execution_count="46" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="iq_FHD1oJv_5" outputId="1988509a-bfaa-45c8-94a7-faac2030ead6"}
``` {.python}
df.info()
```

::: {.output .stream .stdout}
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 244 entries, 0 to 243
    Data columns (total 7 columns):
     #   Column      Non-Null Count  Dtype   
    ---  ------      --------------  -----   
     0   total_bill  244 non-null    float64 
     1   tip         244 non-null    float64 
     2   sex         244 non-null    category
     3   smoker      244 non-null    category
     4   day         244 non-null    category
     5   time        244 non-null    category
     6   size        244 non-null    int64   
    dtypes: category(4), float64(2), int64(1)
    memory usage: 7.4 KB
:::
:::

::: {.cell .code execution_count="47" colab="{\"height\":355,\"base_uri\":\"https://localhost:8080/\"}" id="kfuiUAd_Jx9P" outputId="6b6c9ba9-4b38-45b6-e0fb-43251faa97f8"}
``` {.python}
x = df['total_bill']
y = df['tip']

sns.scatterplot(x,y)
```

::: {.output .stream .stderr}
    /usr/local/lib/python3.7/dist-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
      FutureWarning
:::

::: {.output .execute_result execution_count="47"}
    <matplotlib.axes._subplots.AxesSubplot at 0x7fee8fde5c10>
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/864affbf1d94c9fe1ca786399b9d23060d3927ba.png)
:::
:::

::: {.cell .code execution_count="48" colab="{\"height\":297,\"base_uri\":\"https://localhost:8080/\"}" id="YD5PP4LXJzf5" outputId="00428e09-5e92-499c-d426-9db9165a56c6"}
``` {.python}
sns.boxplot(x="day", y = "tip", hue="sex", data=df, palette="muted")
```

::: {.output .execute_result execution_count="48"}
    <matplotlib.axes._subplots.AxesSubplot at 0x7fee8f5a5690>
:::

::: {.output .display_data}
![](vertopal_568d628f527f41e1b23909914dacd796/f91011367ddb1c19d5e3de0235db8b1677c6ded7.png)
:::
:::

::: {.cell .markdown id="dHoRYITXFcwt"}
:::
