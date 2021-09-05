---


---

<h1 id="simple-linear-regression">Simple Linear Regression</h1>
<p>Mục tiêu của mô hình hồi quy tuyến tính</p>
<ol>
<li>Tìm một mô hình (phương trình) để mô tả một mối liên quan giữa X và Y<br>
*. Với X có thể là volumn (trong dự báo chứng khoán), hoặc giá trị của một technical indicator…<br>
*.  Y có thể là close price.</li>
<li>Điều chỉnh các yếu tố nhiễu</li>
<li>Dự đoán: ví dụ cho mỗi giá trị X làm sao chúng ta có thể dự đoán được giá trị Y.</li>
</ol>
<h2 id="ý-tưởng-đằng-sau-mô-hình-hồi-quy-tuyến-tính">Ý tưởng đằng sau mô hình hồi quy tuyến tính</h2>
<ol>
<li>
<p>tìm giá trị Slope: <span class="katex--display"><span class="katex-display"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mtext>&nbsp;slope&nbsp;</mtext><mo>=</mo><mfrac><mrow><mi mathvariant="normal">Δ</mi><mi>y</mi></mrow><mrow><mi mathvariant="normal">Δ</mi><mi>x</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><msub><mi>y</mi><mn>2</mn></msub><mo>−</mo><msub><mi>y</mi><mn>1</mn></msub></mrow><mrow><msub><mi>x</mi><mn>2</mn></msub><mo>−</mo><msub><mi>x</mi><mn>1</mn></msub></mrow></mfrac></mrow><annotation encoding="application/x-tex">
\text { slope }=\frac{\Delta y}{\Delta x}=\frac{y_{2}-y_{1}}{x_{2}-x_{1}}
</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord text"><span class="mord">&nbsp;slope&nbsp;</span></span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 2.04633em; vertical-align: -0.686em;"></span><span class="mord"><span class="mopen nulldelimiter"></span><span class="mfrac"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.36033em;"><span class="" style="top: -2.314em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord">Δ</span><span class="mord mathnormal">x</span></span></span><span class="" style="top: -3.23em;"><span class="pstrut" style="height: 3em;"></span><span class="frac-line" style="border-bottom-width: 0.04em;"></span></span><span class="" style="top: -3.677em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord">Δ</span><span class="mord mathnormal" style="margin-right: 0.03588em;">y</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.686em;"><span class=""></span></span></span></span></span><span class="mclose nulldelimiter"></span></span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 2.09633em; vertical-align: -0.836em;"></span><span class="mord"><span class="mopen nulldelimiter"></span><span class="mfrac"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.26033em;"><span class="" style="top: -2.314em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord"><span class="mord mathnormal">x</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: 0em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">2</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">−</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mord"><span class="mord mathnormal">x</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: 0em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span></span></span><span class="" style="top: -3.23em;"><span class="pstrut" style="height: 3em;"></span><span class="frac-line" style="border-bottom-width: 0.04em;"></span></span><span class="" style="top: -3.677em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord"><span class="mord mathnormal" style="margin-right: 0.03588em;">y</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: -0.03588em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">2</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">−</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mord"><span class="mord mathnormal" style="margin-right: 0.03588em;">y</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.301108em;"><span class="" style="top: -2.55em; margin-left: -0.03588em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">1</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.15em;"><span class=""></span></span></span></span></span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.836em;"><span class=""></span></span></span></span></span><span class="mclose nulldelimiter"></span></span></span></span></span></span></span></p>
</li>
<li>
<p>Tìm giá trị khởi đầu (intercept) của y khi x=0</p>
</li>
</ol>
<h3 id="simple-linear-regression-model">Simple linear regression model</h3>
<ul>
<li>Y - biến phụ thuộc (dependent variable)
<ul>
<li>là biến liên tục</li>
</ul>
</li>
<li>X - biến độc lập (independent variable)
<ul>
<li>X là biến liên tục hoặc không liên tục.</li>
</ul>
</li>
<li>Mô hình: <span class="katex--display"><span class="katex-display"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mtext>&nbsp;Y&nbsp;</mtext><mo>=</mo><mi>α</mi><mo>+</mo><mi>β</mi><mi>X</mi><mo>+</mo><mi>ε</mi></mrow><annotation encoding="application/x-tex"> \text { Y } = \alpha + \beta X +  \varepsilon</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord text"><span class="mord">&nbsp;Y&nbsp;</span></span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right: 0.277778em;"></span></span><span class="base"><span class="strut" style="height: 0.66666em; vertical-align: -0.08333em;"></span><span class="mord mathnormal" style="margin-right: 0.0037em;">α</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">+</span><span class="mspace" style="margin-right: 0.222222em;"></span></span><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.07847em;">βX</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">+</span><span class="mspace" style="margin-right: 0.222222em;"></span></span><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal">ε</span></span></span></span></span></span><br>
<strong>Trong đó:</strong><br>
<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>α</mi></mrow><annotation encoding="application/x-tex">\alpha</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal" style="margin-right: 0.0037em;">α</span></span></span></span></span> : intercept }<br>
<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.05278em;">β</span></span></span></span></span> : slope/gradient<br>
<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>ε</mi></mrow><annotation encoding="application/x-tex">\varepsilon</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal">ε</span></span></span></span></span>: sai số ngẫu nhiên (random error - những giao động về Y trong mỗi giá trị X</li>
</ul>
<h3 id="giả-định-về-hồi-quy-tuyến-tính">Giả định về hồi quy tuyến tính</h3>
<ul>
<li>Mối liên quan giữa X và Y là tuyến tính về tham số.</li>
<li>X không có sai số ngẫu nhiên</li>
<li>Giá trị của Y độc lập với nhau</li>
<li>Sai số ngẫu nhiên (e): phân bố chuẩn, trung bình 0, phương sai bất biến.</li>
</ul>
<h3 id="ước-tính-một-tham-số">Ước tính một tham số</h3>
<p><strong>Mục tiêu của ước tính tham số</strong></p>
<ul>
<li>Mô hình: Y = <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>α</mi></mrow><annotation encoding="application/x-tex">\alpha</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal" style="margin-right: 0.0037em;">α</span></span></span></span></span> + <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.05278em;">β</span></span></span></span></span>X +  <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>ε</mi></mrow><annotation encoding="application/x-tex">\varepsilon</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal">ε</span></span></span></span></span></li>
<li>Chúng ta không biết <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>α</mi></mrow><annotation encoding="application/x-tex">\alpha</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal" style="margin-right: 0.0037em;">α</span></span></span></span></span> và <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.05278em;">β</span></span></span></span></span>. Nhưng có thể dùng dữ liệu thí nghiệm/thực tế để ước tính 2 tham số đó.</li>
<li>Estimate của <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>α</mi></mrow><annotation encoding="application/x-tex">\alpha</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.43056em; vertical-align: 0em;"></span><span class="mord mathnormal" style="margin-right: 0.0037em;">α</span></span></span></span></span> và <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.05278em;">β</span></span></span></span></span> là a và b</li>
</ul>
<h4 id="tiêu-chuẩn-tìm-tham-số-tốt-nhất">Tiêu chuẩn tìm tham số tốt nhất</h4>
<p><img src="https://github.com/chauitvn/chaunguyen.github.io/blob/efe860a05a2bdf45f5f480e7802159f7420c76a0/simple_linear_regression/tieuchuantimthamso_example.png" alt="enter image description here"><br>
tìm công thức để tính a và b sao cho tổng <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mi>d</mi><mn>2</mn></msup></mrow><annotation encoding="application/x-tex">d^{2}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord"><span class="mord mathnormal">d</span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mord mtight">2</span></span></span></span></span></span></span></span></span></span></span></span></span> là nhỏ nhất =&gt; Least square method = Bình phương nhỏ nhất</p>
<h3 id="python-packages-to-perform-regressions">Python Packages to Perform Regressions</h3>
<ul>
<li>
<p>In statsmodels:</p>
<p>import statsmodels.api as sm<br>
sm.OLS(y,x).fit()</p>
</li>
<li>
<p>In numpy:</p>
<p>np.polyfit(x,y, deg =1)</p>
</li>
<li>
<p>In Pandas:</p>
<p>pd.ols(y, x)</p>
</li>
<li>
<p>In scipy:</p>
<p>from scipy import stats<br>
stats.linregression(x,y)</p>
</li>
</ul>
<h3 id="ví-dụ-regression-of-small-cap-returns-on-large-cap">Ví dụ: Regression of Small Cap Returns on Large Cap</h3>
<ul>
<li>
<p>import the statsmodels module</p>
<p>import statsmodels.api as sm</p>
</li>
<li>
<p>as before, compute percentage changes in both series</p>
<p>df[“SPX_Ret”] = df[‘SPX_Prices’].ptc_change()<br>
df[“R2000_Ret”] = df[‘R2000_Prices’].ptc_change()</p>
</li>
<li>
<p>add a constant to the DataFrame for the regression intercept</p>
<p>df = sm.add_constant(df)</p>
</li>
<li>
<p>Notice that the first row of return is NaN =&gt; we should to delete them through .dropna() function.</p>
</li>
<li>
<p>Run the regression</p>
<p>results = sm.OLS(df[‘R2000_Ret’], df[[‘const’, ‘SPX_Ret’]]).fit()<br>
print(results.summary())</p>
</li>
</ul>
<p>the first argument of the statsmodel regression is the series that represents the dependent variable y, and the next argument contains the independent variable or variables.</p>
<p>In this case, the dependent variable is the <strong>R200 returns</strong> and the independent variables are the constant and <strong>SPX returns</strong>.</p>
<p>The method “fit” runs the regression and results are saved in a class instance called results.</p>
<ul>
<li>Regression output:<br>
<img src="https://github.com/chauitvn/chaunguyen.github.io/blob/7cd15923a7ae00a72dd9cc1434697a7c1fccfcac/simple_linear_regression/Regression_Output.png" alt="enter image description here"></li>
</ul>
<p>There are several important items that we need to focus on:</p>
<ul>
<li><strong>The coefficent (coef)</strong>: 1.1412 is the slope of the regression, which is also refferred to as <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="mord mathnormal" style="margin-right: 0.05278em;">β</span></span></span></span></span>.</li>
<li>The coefficent (coef) above that is the intercept, which is very close to zero.</li>
</ul>
<p>you can also pull out individual items from results, like:</p>
<ul>
<li>Intercept in <em>results.param[0]</em></li>
<li>Slope in <em>results.param[1]</em></li>
</ul>
<p>Another statistic to take note of is the R-Squared of 0.753<br>
<img src="https://github.com/chauitvn/chaunguyen.github.io/blob/2415e5c8dcd181e74d4d33f7bb53dec7b0a718d2/simple_linear_regression/Regression_R_Square_Output.png" alt="enter image description here"></p>
<h3 id="relationship-between-r-square-and-correlation">Relationship between R-Square and Correlation</h3>
<p>The R-squared also measures how well the linear regression line fits the data.<br>
[corr(x,y)]<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mrow></mrow><mn>2</mn></msup></mrow><annotation encoding="application/x-tex">^2</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord"><span class=""></span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">2</span></span></span></span></span></span></span></span></span></span></span></span> = R<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mrow></mrow><mn>2</mn></msup></mrow><annotation encoding="application/x-tex">^2</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.814108em; vertical-align: 0em;"></span><span class="mord"><span class=""></span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.814108em;"><span class="" style="top: -3.063em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">2</span></span></span></span></span></span></span></span></span></span></span></span> (or R-Squared)</p>
<p>sign(corr) = sign(regression slope)</p>
<p>if the regression line is positively sloped, the correlation is positive and if the regression line is negatively sloped, the correlation is negative.</p>
<ul>
<li>In last example:
<ul>
<li>R-squared = 0.753,</li>
<li>the slope of the regression was positive, so the correlation is then positive the</li>
<li>correlation  = +<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msqrt><mn>0.753</mn></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{0.753}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.13278em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.90722em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord">0.753</span></span></span><span class="" style="top: -2.86722em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702
c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,-10,-9.5,-14
c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54
c44.2,-33.3,65.8,-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10
s173,378,173,378c0.7,0,35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429
c69,-144,104.5,-217.7,106.5,-221
l0 -0
c5.3,-9.3,12,-14,20,-14
H400000v40H845.2724
s-225.272,467,-225.272,467s-235,486,-235,486c-2.7,4.7,-9,7,-19,7
c-6,0,-10,-1,-12,-3s-194,-422,-194,-422s-65,47,-65,47z
M834 80h400000v40h-400000z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.13278em;"><span class=""></span></span></span></span></span></span></span></span></span> = 0.868</li>
</ul>
</li>
</ul>
<h3 id="auto-correlation">Auto-correlation</h3>
<p><strong>What is Auto-correlation?</strong><br>
auto-correlation is the correlation of a single time series with a lagged copy of itself.</p>

<table>
<thead>
<tr>
<th>Series</th>
<th>Lagged Series</th>
</tr>
</thead>
<tbody>
<tr>
<td>5</td>
<td></td>
</tr>
<tr>
<td>10</td>
<td>5</td>
</tr>
<tr>
<td>15</td>
<td>10</td>
</tr>
<tr>
<td>20</td>
<td>15</td>
</tr>
<tr>
<td>…</td>
<td>…</td>
</tr>
</tbody>
</table><p>Often, when we refer to a series’s auto-correlation, we mean the “lag-one” auto-correlation. so when using daily data, the auto-correlation would be the correlation of the series with the same series lagged by one day.</p>
<p><strong>Interpretation of Auto-Correlation</strong><br>
what does it mean when a series has a positive or negative auto-correlation?<br>
with financial time series, <em><strong>when returns have a negative auto-correlation, we say it is "mean reverting"</strong></em> đảo ngược trung bình.<br>
alternatively, <em><strong>if a series has positive auto-correlation, we say it is "trend-following"</strong></em> theo xu hướng.</p>
<p><strong>Traders use auto-correlation to make money</strong></p>
<p>lest you think these concepts of auto-correlation are purely theoretical, they are actually used on Wall Street to make money. Many hedge fund strategies are only slightly more complex versions of mean reversion and momentum strategies. <em><strong>Since stocks have historically had negative auto-correlation over horizons of about a week, one popular strategy is to buy stocks that have gone up</strong></em>. For other assets like commodities and currencies, they have historically had positive autocorrelation over horizons of several months, <em><strong>so the typical hedge fund strategy there is to buy commodities that have gone up in the last several months and sell those commodities that have gone down</strong></em>.</p>
<p><strong>Example of positive auto-correlation: exchange rates</strong></p>
<ul>
<li>
<p>Use daily exchange rates in DataFrame “df” from FRED</p>
</li>
<li>
<p>Convert index to datetime</p>
<p>#convert index to datetime<br>
df.index =pd.to_datetime(df.index)<br>
#downsample from daily to monthly data<br>
df = df.resample(rule=‘M’, how=‘last’)<br>
#compute returns from prices<br>
df[‘Return’] = df[‘Price’].pct_change()<br>
#compute auto-correlation<br>
autocorrelation = df[‘Return’].autocorr()<br>
print(“the autocorrelation is:”, autocorrelation)</p>
</li>
</ul>
<p>Example 2: <strong>A Popular Strategy Using Autocorrelation</strong><br>
One puzzling anomaly with stocks is that investors tend to overreact to news. Following large jumps, either up or down, stock prices tend to reverse. This is described as mean reversion in stock prices: prices tend to bounce back, or revert, towards previous levels after large moves, which are observed over time horizons of about a week. A more mathematical way to describe mean reversion is to say that stock returns are negatively autocorrelated.<br>
This simple idea is actually the basis for a popular hedge fund strategy. If you’re curious to learn more about this hedge fund strategy (although it’s not necessary reading for anything else later in the course)<br>
You’ll look at the autocorrelation of weekly returns of MSFT stock from 2012 to 2017. You’ll start with a DataFrame <code>MSFT</code> of daily prices. You should use the <code>.resample()</code> method to get weekly prices and then compute returns from prices. Use the pandas method <code>.autocorr()</code> to get the autocorrelation and show that the autocorrelation is negative. Note that the <code>.autocorr()</code> method only works on Series, not DataFrames (even DataFrames with one column), so you will have to select the column in the DataFrame.</p>
<pre><code># Convert the daily data to weekly data
MSFT = MSFT.resample(rule='M',  how='last')
# Compute the percentage change of prices
returns = MSFT.pct_change()
# Compute and print the autocorrelation of returns
autocorrelation = returns["Adj Close"].autocorr()
print("The autocorrelation of weekly returns is %4.2f" %(autocorrelation))
</code></pre>
<p>Example 3: <strong>Are Interest Rates Autocorrelated?</strong><br>
When you look at daily changes in interest rates, the autocorrelation is close to zero. However, if you resample the data and look at annual changes, the autocorrelation is negative. This implies that while short term changes in interest rates may be uncorrelated, long term changes in interest rates are negatively autocorrelated. A daily move up or down in interest rates is unlikely to tell you anything about interest rates tomorrow, but a move in interest rates over a year can tell you something about where interest rates are going over the next year. And this makes some economic sense: over long horizons, when interest rates go up, the economy tends to slow down, which consequently causes interest rates to fall, and vice versa.<br>
The DataFrame <code>daily_rates</code> contains daily data of 10-year interest rates from 1962 to 2017.</p>
<pre><code># Compute the daily change in interest rates
daily_diff = daily_rates.diff()
# Compute and print the autocorrelation of daily changes
autocorrelation_daily = daily_diff['US10Y'].autocorr()
print("The autocorrelation of daily interest rate changes is %4.2f" %(autocorrelation_daily))
# Convert the daily data to annual data
yearly_rates = daily_rates.resample(rule='A').last()
# Repeat above for annual data
yearly_diff = yearly_rates.diff()
autocorrelation_yearly = yearly_diff['US10Y'].autocorr()
print("The autocorrelation of annual interest rate changes is %4.2f" %(autocorrelation_yearly))
</code></pre>
<h3 id="auto-correlation-funcion">Auto-correlation funcion</h3>
<p><strong>Plot ACF in Python</strong></p>
<ul>
<li>
<p>import module:</p>
<p>from statsmodels.graphics.tsaplots import plot_acf</p>
</li>
<li>
<p>Plot the ACF<br>
plot_acf(x, lags=20, alpha =0.05)</p>
</li>
</ul>
<p>There are several plot arguments that are:<br>
<strong>lags</strong>: how many lags of the correlation function will be plotted<br>
<strong>alpha</strong>: sets the width of the confidence interval, which is discussed on the next slide.<br>
<img src="https://github.com/chauitvn/chaunguyen.github.io/blob/eff5f742035b3eaf6cc73b0c69e17bd9534d1603/simple_linear_regression/ACF_plot.png" alt="enter image description here"></p>
<ul>
<li>here is an ACF plot that contains confidence intervals for each lags, which is the blue region in the figure.</li>
</ul>
<p><strong>Confidence Interval of ACF</strong></p>
<ul>
<li>Argument alpha sets the width of confidence interval</li>
<li>example alpha = 0.05, that means that if the true auto-correlation at that lag is zero, there is only a 5% change the sample auto-correlation will fall outside that window (blue band)</li>
<li>you will get a wider confidence interval if you set alpha lower, or if you have fewer observations. An approximation to the width of the 95% confidence intervals, if you make some simplifying assumptions, is plus or minus 2 over the square root of the number of observations in your series. +/- 2/<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msqrt><mi>N</mi></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{N}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.113335em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.926665em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord mathnormal" style="margin-right: 0.10903em;">N</span></span></span><span class="" style="top: -2.88666em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702
c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,-10,-9.5,-14
c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54
c44.2,-33.3,65.8,-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10
s173,378,173,378c0.7,0,35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429
c69,-144,104.5,-217.7,106.5,-221
l0 -0
c5.3,-9.3,12,-14,20,-14
H400000v40H845.2724
s-225.272,467,-225.272,467s-235,486,-235,486c-2.7,4.7,-9,7,-19,7
c-6,0,-10,-1,-12,-3s-194,-422,-194,-422s-65,47,-65,47z
M834 80h400000v40h-400000z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.113335em;"><span class=""></span></span></span></span></span></span></span></span></span>. if you don’t want no bands on plot, set alpha =1</li>
</ul>
<p><strong>ACF Values instead of Plot</strong><br>
Besides plotting the ACF, you can also extract its numerical values using a similar Python function.</p>
<pre><code>from statsmodels.tsa.stattools import acf
print(acf(x))
</code></pre>
<p>Example 1:  <strong>Taxing Exercise: Compute the ACF</strong><br>
In the last chapter, you computed autocorrelations with one lag. Often we are interested in seeing the autocorrelation over many lags. The quarterly earnings for H&amp;R Block (ticker symbol HRB) is plotted on the right, and you can see the extreme cyclicality of its earnings. A vast majority of its earnings occurs in the quarter that taxes are due.</p>
<p>You will compute the array of autocorrelations for the H&amp;R Block quarterly earnings that is pre-loaded in the DataFrame <code>HRB</code>. Then, plot the autocorrelation function using the <code>plot_acf</code> module. This plot shows what the autocorrelation function looks like for cyclical earnings data. The ACF at <code>lag=0</code> is always one, of course. In the next exercise, you will learn about the confidence interval for the ACF, but for now, suppress the confidence interval by setting <code>alpha=1</code>.</p>
<pre><code># Import the acf module and the plot_acf module from statsmodels
from  statsmodels.tsa.stattools
import  acf
from  statsmodels.graphics.tsaplots
import  plot_acf
# Compute the acf array of HRB
acf_array = acf(HRB)
print(acf_array)
# Plot the acf function
plot_acf(HRB,  alpha=1)
plt.show()
</code></pre>
<p>Exercise 2: <strong>Are We Confident This Stock is Mean Reverting?</strong><br>
In the last chapter, you saw that the autocorrelation of MSFT’s weekly stock returns was -0.16. That autocorrelation seems large, but is it statistically significant? In other words, can you say that there is less than a 5% chance that we would observe such a large negative autocorrelation if the true autocorrelation were really zero? And are there any autocorrelations at other lags that are significantly different from zero?</p>
<p>Even if the true autocorrelations were zero at all lags, in a finite sample of returns you won’t see the estimate of the autocorrelations exactly zero. In fact, the standard deviation of the sample autocorrelation is 1/<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msqrt><mi>N</mi></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{N}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.113335em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.926665em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord mathnormal" style="margin-right: 0.10903em;">N</span></span></span><span class="" style="top: -2.88666em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702
c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,-10,-9.5,-14
c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54
c44.2,-33.3,65.8,-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10
s173,378,173,378c0.7,0,35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429
c69,-144,104.5,-217.7,106.5,-221
l0 -0
c5.3,-9.3,12,-14,20,-14
H400000v40H845.2724
s-225.272,467,-225.272,467s-235,486,-235,486c-2.7,4.7,-9,7,-19,7
c-6,0,-10,-1,-12,-3s-194,-422,-194,-422s-65,47,-65,47z
M834 80h400000v40h-400000z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.113335em;"><span class=""></span></span></span></span></span></span></span></span></span> where N is the number of observations, so if N=100 , for example, the standard deviation of ACF is 0.1, and since 95% of a normal curve is between +1.96 and -1.96 standard deviations from the mean, the 95% confidence interval is +/- 1.96/<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msqrt><mi>N</mi></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{N}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1.04em; vertical-align: -0.113335em;"></span><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.926665em;"><span class="svg-align" style="top: -3em;"><span class="pstrut" style="height: 3em;"></span><span class="mord" style="padding-left: 0.833em;"><span class="mord mathnormal" style="margin-right: 0.10903em;">N</span></span></span><span class="" style="top: -2.88666em;"><span class="pstrut" style="height: 3em;"></span><span class="hide-tail" style="min-width: 0.853em; height: 1.08em;"><svg width="400em" height="1.08em" viewBox="0 0 400000 1080" preserveAspectRatio="xMinYMin slice"><path d="M95,702
c-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,-10,-9.5,-14
c0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54
c44.2,-33.3,65.8,-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10
s173,378,173,378c0.7,0,35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429
c69,-144,104.5,-217.7,106.5,-221
l0 -0
c5.3,-9.3,12,-14,20,-14
H400000v40H845.2724
s-225.272,467,-225.272,467s-235,486,-235,486c-2.7,4.7,-9,7,-19,7
c-6,0,-10,-1,-12,-3s-194,-422,-194,-422s-65,47,-65,47z
M834 80h400000v40h-400000z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.113335em;"><span class=""></span></span></span></span></span></span></span></span></span>. this approximation only holds when the true auto-correlation are all zero.</p>
<p>You will compute the actual and approximate confidence interval for the ACF, and compare it to the lag-one autocorrelation of -0.16 from the last chapter. The weekly returns of Microsoft is pre-loaded in a DataFrame called <code>returns</code>.</p>
<pre><code># Import the plot_acf module from statsmodels and sqrt from math
from  statsmodels.graphics.tsaplots
import  plot_acf
from  math  import  sqrt
# Compute and print the autocorrelation of MSFT weekly returns
autocorrelation = returns['Adj Close'].autocorr()
print("The autocorrelation of weekly MSFT returns is %4.2f" %(autocorrelation))
# Find the number of observations by taking the length of the returns DataFrame
nobs = len(returns)
# Compute the approximate confidence interval
conf = 1.96/sqrt(nobs)
print("The approximate confidence interval is +/- %4.2f" %(conf))
# Plot the autocorrelation function with 95% confidence intervals and 20 lags using plot_acf
plot_acf(returns,  alpha=0.05,  lags = 20)
plt.show()
</code></pre>
<h3 id="white-noise">White Noise</h3>

