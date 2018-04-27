### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode non decodifica più sequenze di input non valide

|   |   |
|---|---|
|Dettagli|Per impostazione predefinita, i metodi di decodifica non decodificano più una sequenza di input non valido in una stringa UTF-16 non valida. Al contrario, viene restituito l'input originale.|
|Suggerimento|La modifica dell'output del decodificatore è importante solo se si archiviano dati binari anziché dati UTF-16 nelle stringhe. Per controllare questo comportamento in modo esplicito, impostare l'attributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) su <code>true</code> per abilitare il comportamento legacy o su <code>false</code> per abilitare il comportamento corrente.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|

