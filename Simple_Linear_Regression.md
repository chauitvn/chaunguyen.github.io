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
<p>The method “fit” runs the regression and results are saved</p>

