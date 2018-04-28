### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>WPF PackageDigitalSignatureManager の既定のハッシュ アルゴリズムが SHA256 になりました

|   |   |
|---|---|
|説明|<code>System.IO.Packaging.PackageDigitalSignatureManager</code> は、WPF パッケージに関連してデジタル署名の機能を提供します。  .NET Framework 4.7 以前のバージョンでは、パッケージのパーツへの署名に使用される既定のアルゴリズム (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) は SHA1 でした。  最近明らかになった SHA1 のセキュリティに関する懸念事項により、この既定値は .NET Framework 4.7.1 で開始する SHA256 に変更されています。  この変更は、XPS ドキュメントを含むあらゆるパッケージの署名に影響します。|
|提案される解決策|.NET 4.7.1 より前のフレームワーク バージョンを対象とするときにこの変更を利用する開発者または .NET 4.7.1 以上を対象とするときに以前の機能を必要とする開発者は、次の AppContext フラグを適宜設定することができます。  true の値を設定すると、SHA1 が既定のアルゴリズムとして使用され、false の値を設定すると SHA256 が使用されます。<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|スコープ|エッジ|
|Version|4.7.1|
|型|再ターゲット中|
|影響を受ける API|<ul><li><xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType></li></ul>|
