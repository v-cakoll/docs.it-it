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
# <a name="script-blocks-using-msxslscript"></a><span data-ttu-id="a1c33-102">Blocchi di script utilizzando msxsl:script</span><span class="sxs-lookup"><span data-stu-id="a1c33-102">Script Blocks Using msxsl:script</span></span>
<span data-ttu-id="a1c33-103">La classe <xref:System.Xml.Xsl.XslCompiledTransform> supporta lo script incorporato mediante l'elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports embedded scripts using the `msxsl:script` element.</span></span> <span data-ttu-id="a1c33-104">Quando viene caricato il foglio di stile, le funzioni definite vengono compilate in MSIL (Microsoft Intermediate Language) da CodeDOM (Code Document Object Model) e vengono attivate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1c33-104">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by the Code Document Object Model (CodeDOM) and are executed during run time.</span></span> <span data-ttu-id="a1c33-105">L'assembly generato dal blocco di script incorporato è separato rispetto all'assembly generato per il foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="a1c33-105">The assembly generated from the embedded script block is separate than the assembly generated for the style sheet.</span></span>  
  
## <a name="enable-xslt-script"></a><span data-ttu-id="a1c33-106">Abilitazione di script XSLT</span><span class="sxs-lookup"><span data-stu-id="a1c33-106">Enable XSLT Script</span></span>  
 <span data-ttu-id="a1c33-107">Il supporto per gli script incorporati è un'impostazione XSLT facoltativa nella classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-107">Support for embedded scripts is an optional XSLT setting on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="a1c33-108">Per impostazione predefinita, il supporto per gli script è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a1c33-108">Script support is disabled by default.</span></span> <span data-ttu-id="a1c33-109">Per abilitarlo, è necessario creare un oggetto <xref:System.Xml.Xsl.XsltSettings> con la proprietà <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> impostata su `true` e passare tale oggetto al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-109">To enable script support, create an <xref:System.Xml.Xsl.XsltSettings> object with the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> property set to `true` and pass the object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1c33-110">Lo script con XSLT deve essere abilitato solo se è necessario il supporto per gli script e solo all'interno di un ambiente completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="a1c33-110">XSLT scripting should be enabled only if you require script support and you are working in a fully trusted environment.</span></span>  
  
## <a name="msxslscript-element-definition"></a><span data-ttu-id="a1c33-111">Definizione dell'elemento msxsl:script</span><span class="sxs-lookup"><span data-stu-id="a1c33-111">msxsl:script Element Definition</span></span>  
 <span data-ttu-id="a1c33-112">L'elemento `msxsl:script` è un'estensione Microsoft della raccomandazione XSLT 1.0 e presenta la seguente definizione:</span><span class="sxs-lookup"><span data-stu-id="a1c33-112">The `msxsl:script` element is a Microsoft extension to the XSLT 1.0 recommendation and has the following definition:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="a1c33-113">Il prefisso `msxsl` è associato all'URI dello spazio dei nomi `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-113">The `msxsl` prefix is bound to the `urn:schemas-microsoft-com:xslt` namespace URI.</span></span> <span data-ttu-id="a1c33-114">Nel foglio di stile XSLT deve essere inclusa la dichiarazione dello spazio dei nomi `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-114">The style sheet must include the `xmlns:msxsl=urn:schemas-microsoft-com:xslt` namespace declaration.</span></span>  
  
 <span data-ttu-id="a1c33-115">L'attributo `language` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a1c33-115">The `language` attribute is optional.</span></span> <span data-ttu-id="a1c33-116">Il valore dell'attributo è il linguaggio di codice del blocco di codice incorporato.</span><span class="sxs-lookup"><span data-stu-id="a1c33-116">Its value is the code language of the embedded code block.</span></span> <span data-ttu-id="a1c33-117">Il linguaggio è associato al compilatore CodeDOM appropriato tramite il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-117">The language is mapped to the appropriate CodeDOM compiler using the <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a1c33-118">La classe <xref:System.Xml.Xsl.XslCompiledTransform> può supportare qualsiasi linguaggio Microsoft .NET, a condizione che il provider appropriato sia installato nel computer e sia registrato nella sezione system.codedom del file machine.config.</span><span class="sxs-lookup"><span data-stu-id="a1c33-118">The <xref:System.Xml.Xsl.XslCompiledTransform> class can support any Microsoft .NET language, assuming the appropriate provider is installed on the machine and is registered in the system.codedom section of the machine.config file.</span></span> <span data-ttu-id="a1c33-119">Se non viene specificato un attributo `language`, verrà impostato il valore predefinito JScript.</span><span class="sxs-lookup"><span data-stu-id="a1c33-119">If a `language` attribute is not specified, the language defaults to JScript.</span></span> <span data-ttu-id="a1c33-120">Poiché nel nome del linguaggio non viene rilevata la differenza tra maiuscole e minuscole, 'JavaScript' e 'javascript' sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a1c33-120">The language name is not case-sensitive so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="a1c33-121">L'attributo `implements-prefix` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a1c33-121">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="a1c33-122">Questo attributo viene usato per dichiarare uno spazio dei nomi e associarlo al blocco di script.</span><span class="sxs-lookup"><span data-stu-id="a1c33-122">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="a1c33-123">Il valore di questo attributo è il prefisso che rappresenta lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a1c33-123">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="a1c33-124">È possibile definire questo prefisso in un punto qualsiasi di un foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="a1c33-124">This prefix can be defined somewhere in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1c33-125">Quando si usa l'elemento `msxsl:script`, si consiglia che tale script, indipendentemente dal linguaggio, venga inserito all'interno di una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="a1c33-125">When using the `msxsl:script` element, we strongly recommend that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="a1c33-126">Dal momento che può contenere operatori, identificatori o delimitatori per un determinato linguaggio, se non è contenuto in una sezione CDATA, è possibile che lo script venga erroneamente interpretato come XML.</span><span class="sxs-lookup"><span data-stu-id="a1c33-126">Because the script can contain operators, identifiers, or delimiters for a given language, if it is not contained within a CDATA section, it has the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="a1c33-127">Nel seguente XML viene illustrato un modello di sezione CDATA in cui può essere inserito il codice.</span><span class="sxs-lookup"><span data-stu-id="a1c33-127">The following XML shows a template of the CDATA section where code can be placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a><span data-ttu-id="a1c33-128">Funzioni di script</span><span class="sxs-lookup"><span data-stu-id="a1c33-128">Script Functions</span></span>  
 <span data-ttu-id="a1c33-129">È possibile dichiarare le funzioni all'interno dell'elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-129">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="a1c33-130">Quando si dichiara una funzione, questa è contenuta in un blocco di script.</span><span class="sxs-lookup"><span data-stu-id="a1c33-130">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="a1c33-131">I fogli di stile possono contenere più blocchi di script con funzionamento indipendente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="a1c33-131">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="a1c33-132">Ciò significa che, all'interno di un blocco di script, non è possibile chiamare una funzione definita in un altro blocco di script a meno che per quest'ultimo non sia dichiarato lo stesso spazio dei nomi e lo stesso linguaggio di script.</span><span class="sxs-lookup"><span data-stu-id="a1c33-132">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="a1c33-133">Poiché ogni blocco di script può essere scritto nel proprio linguaggio e il blocco viene analizzato in base alle regole grammaticali del parser di quel linguaggio, si consiglia di usare la sintassi corretta per il linguaggio in uso.</span><span class="sxs-lookup"><span data-stu-id="a1c33-133">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser we recommend that you use the correct syntax for the language in use.</span></span> <span data-ttu-id="a1c33-134">Ad esempio, nel caso di un blocco di script di Microsoft C#, si consiglia di usare la sintassi di commento di C#.</span><span class="sxs-lookup"><span data-stu-id="a1c33-134">For example, if you are in a Microsoft C# script block, use the C# comment syntax.</span></span>  
  
 <span data-ttu-id="a1c33-135">Gli argomenti e i valori restituiti che vengono forniti alla funzione possono essere di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="a1c33-135">The supplied arguments and return values to the function can be of any type.</span></span> <span data-ttu-id="a1c33-136">Poiché i tipi W3C XPath sono subset dei tipi CLR (Common Language Runtime), la conversione del tipo viene eseguita per i tipi che non sono considerati come tipi XPath.</span><span class="sxs-lookup"><span data-stu-id="a1c33-136">Because the W3C XPath types are a subset of the common language runtime (CLR) types, type conversion takes place on types that are not considered to be an XPath type.</span></span> <span data-ttu-id="a1c33-137">Nella tabella seguente vengono illustrati i tipi W3C corrispondenti e il tipo CLR equivalente.</span><span class="sxs-lookup"><span data-stu-id="a1c33-137">The following table shows the corresponding W3C types and the equivalent CLR type.</span></span>  
  
|<span data-ttu-id="a1c33-138">Tipo W3C</span><span class="sxs-lookup"><span data-stu-id="a1c33-138">W3C type</span></span>|<span data-ttu-id="a1c33-139">Tipo CLR</span><span class="sxs-lookup"><span data-stu-id="a1c33-139">CLR type</span></span>|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 <span data-ttu-id="a1c33-140">I tipi numerici CLR vengono convertiti nel tipo <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-140">CLR numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="a1c33-141">Il tipo <xref:System.DateTime> viene convertito in <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a1c33-141">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="a1c33-142">e i tipi <xref:System.Xml.XPath.IXPathNavigable> in <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-142"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="a1c33-143">**XPathNavigator[]** viene convertito nel tipo <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="a1c33-143">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="a1c33-144">Per tutti gli altri tipi verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="a1c33-144">All other types throw an error.</span></span>  
  
### <a name="importing-namespaces-and-assemblies"></a><span data-ttu-id="a1c33-145">Importazione di spazi dei nomi e assembly</span><span class="sxs-lookup"><span data-stu-id="a1c33-145">Importing Namespaces and Assemblies</span></span>  
 <span data-ttu-id="a1c33-146">La classe <xref:System.Xml.Xsl.XslCompiledTransform> contiene un set predefinito di assembly e di spazi dei nomi che è supportato per impostazione predefinita dall'elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-146">The <xref:System.Xml.Xsl.XslCompiledTransform> class predefines a set of assemblies and namespaces that are supported by default by the `msxsl:script` element.</span></span> <span data-ttu-id="a1c33-147">Tuttavia, è possibile usare le classi e i membri appartenenti a uno spazio dei nomi che non è presente nell'elenco predefinito importando l'assembly e lo spazio dei nomi nel blocco `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-147">However, you can use classes and members belonging to a namespace that is not on the predefined list by importing the assembly and namespace in `msxsl:script` block.</span></span>  
  
#### <a name="assemblies"></a><span data-ttu-id="a1c33-148">Assembly</span><span class="sxs-lookup"><span data-stu-id="a1c33-148">Assemblies</span></span>  
 <span data-ttu-id="a1c33-149">Per impostazione predefinita, viene fatto riferimento ai due assembly seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1c33-149">The following two assemblies are referenced by default:</span></span>  
  
- <span data-ttu-id="a1c33-150">System.dll</span><span class="sxs-lookup"><span data-stu-id="a1c33-150">System.dll</span></span>  
  
- <span data-ttu-id="a1c33-151">System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="a1c33-151">System.Xml.dll</span></span>  
  
- <span data-ttu-id="a1c33-152">Microsoft.VisualBasic.dll (se il linguaggio di script è VB)</span><span class="sxs-lookup"><span data-stu-id="a1c33-152">Microsoft.VisualBasic.dll (when the script language is VB)</span></span>  
  
 <span data-ttu-id="a1c33-153">È possibile importare ulteriori assembly usando l'elemento `msxsl:assembly`,</span><span class="sxs-lookup"><span data-stu-id="a1c33-153">You can import the additional assemblies using the `msxsl:assembly` element.</span></span> <span data-ttu-id="a1c33-154">incluso l'assembly quando il foglio di stile è compilato.</span><span class="sxs-lookup"><span data-stu-id="a1c33-154">This includes the assembly when the style sheet is compiled.</span></span> <span data-ttu-id="a1c33-155">L'elemento `msxsl:assembly` presenta la seguente definizione:</span><span class="sxs-lookup"><span data-stu-id="a1c33-155">The `msxsl:assembly` element has the following definition:</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="a1c33-156">L'attributo `name` contiene il nome dell'assembly, mentre l'attributo `href` ne contiene il percorso.</span><span class="sxs-lookup"><span data-stu-id="a1c33-156">The `name` attribute contains the name of the assembly and the `href` attribute contains the path to the assembly.</span></span> <span data-ttu-id="a1c33-157">Il nome dell'assembly può essere un nome completo, ad esempio "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", oppure un nome breve, ad esempio "System.Web".</span><span class="sxs-lookup"><span data-stu-id="a1c33-157">The assembly name can be a full name, such as "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", or a short name, such as "System.Web".</span></span>  
  
#### <a name="namespaces"></a><span data-ttu-id="a1c33-158">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="a1c33-158">Namespaces</span></span>  
 <span data-ttu-id="a1c33-159">Per impostazione predefinita sono inclusi i seguenti spazi dei nomi:</span><span class="sxs-lookup"><span data-stu-id="a1c33-159">The following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="a1c33-160">System</span><span class="sxs-lookup"><span data-stu-id="a1c33-160">System</span></span>  
  
- <span data-ttu-id="a1c33-161">System.Collection</span><span class="sxs-lookup"><span data-stu-id="a1c33-161">System.Collection</span></span>  
  
- <span data-ttu-id="a1c33-162">System.Text</span><span class="sxs-lookup"><span data-stu-id="a1c33-162">System.Text</span></span>  
  
- <span data-ttu-id="a1c33-163">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="a1c33-163">System.Text.RegularExpressions</span></span>  
  
- <span data-ttu-id="a1c33-164">System.Xml</span><span class="sxs-lookup"><span data-stu-id="a1c33-164">System.Xml</span></span>  
  
- <span data-ttu-id="a1c33-165">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="a1c33-165">System.Xml.Xsl</span></span>  
  
- <span data-ttu-id="a1c33-166">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="a1c33-166">System.Xml.XPath</span></span>  
  
- <span data-ttu-id="a1c33-167">Microsoft.VisualBasic (se il linguaggio di script è VB)</span><span class="sxs-lookup"><span data-stu-id="a1c33-167">Microsoft.VisualBasic (when the script language is VB)</span></span>  
  
 <span data-ttu-id="a1c33-168">È possibile aggiungere il supporto per ulteriori spazi di nomi usando l'attributo `namespace`.</span><span class="sxs-lookup"><span data-stu-id="a1c33-168">You can add support for additional namespaces using the `namespace` attribute.</span></span> <span data-ttu-id="a1c33-169">Il valore dell'attributo è il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a1c33-169">The attribute value is the name of the namespace.</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a><span data-ttu-id="a1c33-170">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1c33-170">Example</span></span>  
 <span data-ttu-id="a1c33-171">Nell'esempio seguente viene usato uno script incorporato per calcolare la circonferenza di un cerchio di cui viene fornito il raggio.</span><span class="sxs-lookup"><span data-stu-id="a1c33-171">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a><span data-ttu-id="a1c33-172">number.xml</span><span class="sxs-lookup"><span data-stu-id="a1c33-172">number.xml</span></span>  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a><span data-ttu-id="a1c33-173">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="a1c33-173">calc.xsl</span></span>  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="a1c33-174">Output</span><span class="sxs-lookup"><span data-stu-id="a1c33-174">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1c33-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1c33-175">See also</span></span>

- [<span data-ttu-id="a1c33-176">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="a1c33-176">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="a1c33-177">Generazione e compilazione dinamica di codice sorgente</span><span class="sxs-lookup"><span data-stu-id="a1c33-177">Dynamic Source Code Generation and Compilation</span></span>](../../../framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
