# PostgreSQL

## Типы данных

### Основные типы данных

<table>
  <tr>
    <td></td>
    <td>Name</td>
    <td>Bytes</td>
    <td>Range</td>
  </tr>
  <tr>
    <td rowspan="6">Integral</br>Numbers</td>
    <td>smallint</td>
    <td>2</td>
    <td>-32'768 ... +32'768</td>
  </tr>
  <tr>
    <td>integer</td>
    <td>4</td>
    <td>-2'147'483'648 ... +2'147'483'647</td>
  </tr>
  <tr>
    <td>bigint</td>
    <td>8</td>
    <td>-9'223'372'036'854'775'808 ... 9'223'372'036'854'775'807</td>
  </tr>
  <tr>
    <td>smallserial</td>
    <td>2</td>
    <td>1 ... 32'767</td>
  </tr>
  <tr>
    <td>serial</td>
    <td>4</td>
    <td>1 ... 2'147'483'647</td>
  </tr>
  <tr>
    <td>bigserial</td>
    <td>8</td>
    <td>1 ... 9'223'372'036'854'775'807</td>
  </tr>
  <tr>
    <td rowspan="3">Real</br>Numbers</td>
    <td>decimal / numeric</td>
    <td>variable</td>
    <td>+-3.4 * 10^38 ... +3.4 * 10^38</td>
  </tr>
  <tr>
    <td>real /</br> float4</td>
    <td>4</td>
    <td>6 decimal digits precision</td>
  </tr>
  <tr>
    <td>double /</br> precision /</br> float8 /</br> float</td>
    <td>8</td>
    <td>15 decimal digits precision</td>
  </tr>
  <tr>
    <td rowspan="3">Character</td>
    <td>char</td>
    <td>variable</td>
    <td>based on encoding</td>
  </tr>
  <tr>
    <td>varchar</td>
    <td>variable</td>
    <td>based on encoding</td>
  </tr>
  <tr>
    <td>text</td>
    <td>variable</td>
    <td>based on encoding</td>
  </tr>
  <tr>
    <td>Logical</td>
    <td>Boolean /<br/> bool</td>
    <td>1</td>
    <td>True / False</td>
  </tr>
  <tr>
    <td rowspan="6">Temporal</td>
    <td>date</td>
    <td>4</td>
    <td>4731 BC ... 294'276 AD</td>
  </tr>
  <tr>
    <td>time</td>
    <td>8</td>
    <td>00:00:00 ... 24:00:00</td>
  </tr>
  <tr>
    <td>timestamp</td>
    <td>8</td>
    <td>4731 BC ... 294'276 AD</td>
  <tr>
  </tr>
    <td>interval</td>
    <td>16</td>
    <td>-178'000'000 ... +178'000'000</td>
  </tr>
  <tr>
    <td>timestamptz</br>(timestamp + timezone)</td>
    <td>8</td>
    <td>4731 BC ... 294'276 AD + tz</td>
  <tr>
</table>

### Сложные типы данных

- Arrays;
- JSON;
- XML;
- Геометрические типы;
- Произвольные типы;
- NULL (отсутствие данных).
