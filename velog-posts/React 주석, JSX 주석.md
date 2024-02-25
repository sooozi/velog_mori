<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/17c20d90-48fa-44da-84f4-7f0385149884/image.png" />
매일 리액트를 사용할 때마다 헷갈리던 주석!
오늘은 리액트 주석을 뽀개러 가봅시다 🕊️</p>
<blockquote>
<h2 id="01-react-주석">01. React 주석</h2>
</blockquote>
<p>자바스크립트와 동일한 방법으로 주석처리를 해줍니다.
<span style="color: #38c491;">🥏 한 줄 주석</span> : //
<span style="color: #38c491;">🥏 여러 줄 주석</span> : /* */</p>
<pre><code>&lt;script type=&quot;text/babel&quot;&gt;
    function App() {
      // const [minutes, setMinutes] = React.useState();
      const onChange = (event) =&gt; {
        setMinutes(event.target.value);
      };
      return (
        &lt;div /&gt;
        );
      }
  &lt;/script&gt;</code></pre><blockquote>
<h2 id="02-jsx-주석">02. JSX 주석</h2>
</blockquote>
<p>자바스크립트 여러줄 주석에 {}를 추가합니다.</p>
<pre><code> &lt;script type=&quot;text/babel&quot;&gt;
    function App() {
    //React 주석
    // const [minutes, setMinutes] = React.useState();
      const onChange = (event) =&gt; {
        setMinutes(event.target.value);
      };
      return (
        &lt;div&gt;
        {/*JSX 주석*/}
          {/*&lt;h1 className=&quot;tit&quot;&gt;🧮 Super Converter 🧮&lt;/h1&gt;*/}
        &lt;/div&gt;
        );
      }
  &lt;/script&gt;</code></pre>