---
title: Blocchi di script utilizzando msxsl:script
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: e65308f097e81d844cb04b1ebd5cbcdd8a3aadad
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291994"
---
# <a name="script-blocks-using-msxslscript"></a>Blocchi di script utilizzando msxsl:script
La classe <xref:System.Xml.Xsl.XslCompiledTransform> supporta lo script incorporato mediante l'elemento `msxsl:script`. Quando viene caricato il foglio di stile, le funzioni definite vengono compilate in MSIL (Microsoft Intermediate Language) da CodeDOM (Code Document Object Model) e vengono attivate in fase di esecuzione. L'assembly generato dal blocco di script incorporato è separato rispetto all'assembly generato per il foglio di stile.  
  
## <a name="enable-xslt-script"></a>Abilitazione di script XSLT  
 Il supporto per gli script incorporati è un'impostazione XSLT facoltativa nella classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per impostazione predefinita, il supporto per gli script è disabilitato. Per abilitarlo, è necessario creare un oggetto <xref:System.Xml.Xsl.XsltSettings> con la proprietà <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> impostata su `true` e passare tale oggetto al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
> [!NOTE]
> Lo script con XSLT deve essere abilitato solo se è necessario il supporto per gli script e solo all'interno di un ambiente completamente attendibile.  
  
## <a name="msxslscript-element-definition"></a>Definizione dell'elemento msxsl:script  
 L'elemento `msxsl:script` è un'estensione Microsoft della raccomandazione XSLT 1.0 e presenta la seguente definizione:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 Il prefisso `msxsl` è associato all'URI dello spazio dei nomi `urn:schemas-microsoft-com:xslt`. Nel foglio di stile XSLT deve essere inclusa la dichiarazione dello spazio dei nomi `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.  
  
 L'attributo `language` è facoltativo. Il valore dell'attributo è il linguaggio di codice del blocco di codice incorporato. Il linguaggio è associato al compilatore CodeDOM appropriato tramite il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>. La classe <xref:System.Xml.Xsl.XslCompiledTransform> può supportare qualsiasi linguaggio Microsoft .NET, a condizione che il provider appropriato sia installato nel computer e sia registrato nella sezione system.codedom del file machine.config. Se non viene specificato un attributo `language`, verrà impostato il valore predefinito JScript. Poiché nel nome del linguaggio non viene rilevata la differenza tra maiuscole e minuscole, 'JavaScript' e 'javascript' sono equivalenti.  
  
 L'attributo `implements-prefix` è obbligatorio. Questo attributo viene usato per dichiarare uno spazio dei nomi e associarlo al blocco di script. Il valore di questo attributo è il prefisso che rappresenta lo spazio dei nomi. È possibile definire questo prefisso in un punto qualsiasi di un foglio di stile.  
  
> [!NOTE]
> Quando si usa l'elemento `msxsl:script`, si consiglia che tale script, indipendentemente dal linguaggio, venga inserito all'interno di una sezione CDATA. Dal momento che può contenere operatori, identificatori o delimitatori per un determinato linguaggio, se non è contenuto in una sezione CDATA, è possibile che lo script venga erroneamente interpretato come XML. Nel seguente XML viene illustrato un modello di sezione CDATA in cui può essere inserito il codice.  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a>Funzioni di script  
 È possibile dichiarare le funzioni all'interno dell'elemento `msxsl:script`. Quando si dichiara una funzione, questa è contenuta in un blocco di script. I fogli di stile possono contenere più blocchi di script con funzionamento indipendente l'uno dall'altro. Ciò significa che, all'interno di un blocco di script, non è possibile chiamare una funzione definita in un altro blocco di script a meno che per quest'ultimo non sia dichiarato lo stesso spazio dei nomi e lo stesso linguaggio di script. Poiché ogni blocco di script può essere scritto nel proprio linguaggio e il blocco viene analizzato in base alle regole grammaticali del parser di quel linguaggio, si consiglia di usare la sintassi corretta per il linguaggio in uso. Ad esempio, nel caso di un blocco di script di Microsoft C#, si consiglia di usare la sintassi di commento di C#.  
  
 Gli argomenti e i valori restituiti che vengono forniti alla funzione possono essere di qualsiasi tipo. Poiché i tipi W3C XPath sono subset dei tipi CLR (Common Language Runtime), la conversione del tipo viene eseguita per i tipi che non sono considerati come tipi XPath. Nella tabella seguente vengono illustrati i tipi W3C corrispondenti e il tipo CLR equivalente.  
  
|Tipo W3C|Tipo CLR|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 I tipi numerici CLR vengono convertiti nel tipo <xref:System.Double>. Il tipo <xref:System.DateTime> viene convertito in <xref:System.String> e i tipi <xref:System.Xml.XPath.IXPathNavigable> in <xref:System.Xml.XPath.XPathNavigator>. **XPathNavigator[]** viene convertito nel tipo <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Per tutti gli altri tipi verrà generato un errore.  
  
### <a name="importing-namespaces-and-assemblies"></a>Importazione di spazi dei nomi e assembly  
 La classe <xref:System.Xml.Xsl.XslCompiledTransform> contiene un set predefinito di assembly e di spazi dei nomi che è supportato per impostazione predefinita dall'elemento `msxsl:script`. Tuttavia, è possibile usare le classi e i membri appartenenti a uno spazio dei nomi che non è presente nell'elenco predefinito importando l'assembly e lo spazio dei nomi nel blocco `msxsl:script`.  
  
#### <a name="assemblies"></a>Assembly  
 Per impostazione predefinita, viene fatto riferimento ai due assembly seguenti:  
  
- System.dll  
  
- System.Xml.dll  
  
- Microsoft.VisualBasic.dll (se il linguaggio di script è VB)  
  
 È possibile importare ulteriori assembly usando l'elemento `msxsl:assembly`, incluso l'assembly quando il foglio di stile è compilato. L'elemento `msxsl:assembly` presenta la seguente definizione:  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 L'attributo `name` contiene il nome dell'assembly, mentre l'attributo `href` ne contiene il percorso. Il nome dell'assembly può essere un nome completo, ad esempio "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", oppure un nome breve, ad esempio "System.Web".  
  
#### <a name="namespaces"></a>Spazi dei nomi  
 Per impostazione predefinita sono inclusi i seguenti spazi dei nomi:  
  
- System  
  
- System.Collection  
  
- System.Text  
  
- System.Text.RegularExpressions  
  
- System.Xml  
  
- System.Xml.Xsl  
  
- System.Xml.XPath  
  
- Microsoft.VisualBasic (se il linguaggio di script è VB)  
  
 È possibile aggiungere il supporto per ulteriori spazi di nomi usando l'attributo `namespace`. Il valore dell'attributo è il nome dello spazio dei nomi.  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato uno script incorporato per calcolare la circonferenza di un cerchio di cui viene fornito il raggio.  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a>number.xml  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a>calc.xsl  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a>Output  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Trasformazioni XSLT](xslt-transformations.md)
- [Generazione e compilazione dinamica di codice sorgente](../../../framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
