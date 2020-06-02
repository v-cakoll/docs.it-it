---
title: Scripting dei fogli di stile XSLT con <msxsl:script>
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 60e2541b-0cea-4b2e-a4fa-85f4c50f1bef
ms.openlocfilehash: aef2471a375469f7cd4dff27084b305ef9394d5e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291968"
---
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a><span data-ttu-id="815fb-102">Scripting del foglio di stile XSLT con\<msxsl:script></span><span class="sxs-lookup"><span data-stu-id="815fb-102">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>
<span data-ttu-id="815fb-103">La classe <xref:System.Xml.Xsl.XslTransform> supporta lo scripting incorporato mediante l'elemento `script`.</span><span class="sxs-lookup"><span data-stu-id="815fb-103">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="815fb-104">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="815fb-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="815fb-105">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="815fb-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="815fb-106">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="815fb-106">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="815fb-107">La classe <xref:System.Xml.Xsl.XslTransform> supporta lo scripting incorporato mediante l'elemento `script`.</span><span class="sxs-lookup"><span data-stu-id="815fb-107">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span> <span data-ttu-id="815fb-108">Dal momento che, quando viene caricato il foglio di stile, le funzioni definite vengono compilate nel linguaggio MSIL (Microsoft Intermediate Language) mediante l'incapsulamento in una definizione della classe, non si verifica alcuna riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="815fb-108">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by being wrapped in a class definition and have no performance loss as a result.</span></span>  
  
 <span data-ttu-id="815fb-109">L'elemento `<msxsl:script>` viene definito di seguito:</span><span class="sxs-lookup"><span data-stu-id="815fb-109">The `<msxsl:script>` element is defined below:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="815fb-110">dove `msxsl` è un prefisso associato allo spazio dei nomi `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="815fb-110">where `msxsl` is a prefix bound to the namespace `urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="815fb-111">L' `language` attributo non è obbligatorio, ma se specificato, il relativo valore deve essere uno dei seguenti: `C#` , `VB` , `JScript` , `JavaScript` , `VisualBasic` o `CSharp` .</span><span class="sxs-lookup"><span data-stu-id="815fb-111">The `language` attribute is not mandatory, but if specified, its value must be one of the following: `C#`, `VB`, `JScript`, `JavaScript`, `VisualBasic`, or `CSharp`.</span></span> <span data-ttu-id="815fb-112">Se omesso, il linguaggio viene impostato su JScript.</span><span class="sxs-lookup"><span data-stu-id="815fb-112">If not specified, the language defaults to JScript.</span></span> <span data-ttu-id="815fb-113">Poiché nel `language-name` non viene fatta distinzione tra maiuscole e minuscole, "JavaScript" e "javascript" si equivalgono.</span><span class="sxs-lookup"><span data-stu-id="815fb-113">The `language-name` is not case-sensitive, so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="815fb-114">L'attributo `implements-prefix` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="815fb-114">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="815fb-115">Questo attributo viene usato per dichiarare uno spazio dei nomi e associarlo al blocco di script.</span><span class="sxs-lookup"><span data-stu-id="815fb-115">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="815fb-116">Il valore di questo attributo è il prefisso che rappresenta lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="815fb-116">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="815fb-117">È possibile definire lo spazio dei nomi in un punto qualsiasi di un foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="815fb-117">This namespace can be defined somewhere in a style sheet.</span></span>  
  
 <span data-ttu-id="815fb-118">Poiché l'elemento `msxsl:script` appartiene allo spazio dei nomi `urn:schemas-microsoft-com:xslt`, il foglio di stile deve includere la dichiarazione dello spazio dei nomi `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="815fb-118">Because the `msxsl:script` element belongs to the namespace `urn:schemas-microsoft-com:xslt`, the style sheet must include the namespace declaration `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="815fb-119">Se il chiamante dello script non dispone dell'autorizzazione di accesso <xref:System.Security.Permissions.SecurityPermissionFlag>, lo script presente nel foglio di stile non verrà compilato e non sarà possibile eseguire la chiamata a <xref:System.Xml.Xsl.XslTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="815fb-119">If the caller of the script does not have <xref:System.Security.Permissions.SecurityPermissionFlag> access permission, then the script in a style sheet will never compile and the call to <xref:System.Xml.Xsl.XslTransform.Load%2A> will fail.</span></span>  
  
 <span data-ttu-id="815fb-120">Se il chiamante dispone dell'autorizzazione `UnmanagedCode`, lo script verrà compilato, ma le operazioni consentite dipenderanno dall'evidenza fornita in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="815fb-120">If the caller has `UnmanagedCode` permission, the script compiles, but the operations that are allowed are dependent on the evidence that is supplied at load time.</span></span>  
  
 <span data-ttu-id="815fb-121">Se per il caricamento del foglio di stile si usa uno dei metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> che accettano un tipo <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>, è necessario usare il metodo di overload <xref:System.Xml.Xsl.XslTransform.Load%2A> che accetta un parametro <xref:System.Security.Policy.Evidence> come argomento.</span><span class="sxs-lookup"><span data-stu-id="815fb-121">If you are using one of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlReader> or <xref:System.Xml.XPath.XPathNavigator> to load the style sheet, you need to use the <xref:System.Xml.Xsl.XslTransform.Load%2A> overload that takes an <xref:System.Security.Policy.Evidence> parameter as one of its arguments.</span></span> <span data-ttu-id="815fb-122">Per fornire l'evidenza, il chiamante deve disporre dell'autorizzazione <xref:System.Security.Permissions.SecurityPermissionFlag> per fornire il parametro `Evidence` per l'assembly dello script.</span><span class="sxs-lookup"><span data-stu-id="815fb-122">To provide evidence, the caller must have <xref:System.Security.Permissions.SecurityPermissionFlag> permission to supply `Evidence` for the script assembly.</span></span> <span data-ttu-id="815fb-123">Se il chiamante non dispone di questa autorizzazione, il parametro `Evidence` può essere impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="815fb-123">If the caller does not have this permission, then they can set the `Evidence` parameter to `null`.</span></span> <span data-ttu-id="815fb-124">In questo caso la funzione <xref:System.Xml.Xsl.XslTransform.Load%2A> non viene eseguita se vengono rilevati degli script.</span><span class="sxs-lookup"><span data-stu-id="815fb-124">This causes the <xref:System.Xml.Xsl.XslTransform.Load%2A> function to fail if it finds script.</span></span> <span data-ttu-id="815fb-125">L'autorizzazione `ControlEvidence` è molto efficace e deve essere concessa esclusivamente a codice completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="815fb-125">The `ControlEvidence` permission is considered a very powerful permission that should only be granted to highly trusted code.</span></span>  
  
 <span data-ttu-id="815fb-126">Per ottenere l'evidenza dall'assembly, usare `this.GetType().Assembly.Evidence`.</span><span class="sxs-lookup"><span data-stu-id="815fb-126">To get the evidence from your assembly, use `this.GetType().Assembly.Evidence`.</span></span> <span data-ttu-id="815fb-127">Per ottenere l'evidenza da un URI (Uniform Resource Identifier), usare `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span><span class="sxs-lookup"><span data-stu-id="815fb-127">To get the evidence from a Uniform Resource Identifier (URI), use `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span></span>  
  
 <span data-ttu-id="815fb-128">Se si usano i metodi <xref:System.Xml.Xsl.XslTransform.Load%2A> che accettano un tipo <xref:System.Xml.XmlResolver> e non dispongono del parametro `Evidence`, l'impostazione predefinita per l'area di sicurezza dell'assembly è Attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="815fb-128">If you use <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlResolver> but no `Evidence`, the security zone for the assembly defaults to Full Trust.</span></span> <span data-ttu-id="815fb-129">Per altre informazioni, vedere <xref:System.Security.SecurityZone> e [Set di autorizzazioni denominati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="815fb-129">For more information, see <xref:System.Security.SecurityZone> and [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="815fb-130">È possibile dichiarare le funzioni all'interno dell'elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="815fb-130">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="815fb-131">Nella tabella seguente sono illustrati gli spazi dei nomi supportati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="815fb-131">The following table shows the namespaces that are supported by default.</span></span> <span data-ttu-id="815fb-132">È possibile usare classi che non sono comprese negli spazi dei nomi elencati.</span><span class="sxs-lookup"><span data-stu-id="815fb-132">You can use classes outside the listed namespaces.</span></span> <span data-ttu-id="815fb-133">Tuttavia, è necessario che tali classi siano complete.</span><span class="sxs-lookup"><span data-stu-id="815fb-133">However, these classes must be fully qualified.</span></span>  
  
|<span data-ttu-id="815fb-134">Spazi dei nomi predefiniti</span><span class="sxs-lookup"><span data-stu-id="815fb-134">Default Namespaces</span></span>|<span data-ttu-id="815fb-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="815fb-135">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="815fb-136">System</span><span class="sxs-lookup"><span data-stu-id="815fb-136">System</span></span>|<span data-ttu-id="815fb-137">Classe di sistema.</span><span class="sxs-lookup"><span data-stu-id="815fb-137">System class.</span></span>|  
|<span data-ttu-id="815fb-138">System.Collection</span><span class="sxs-lookup"><span data-stu-id="815fb-138">System.Collection</span></span>|<span data-ttu-id="815fb-139">Classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="815fb-139">Collection classes.</span></span>|  
|<span data-ttu-id="815fb-140">System.Text</span><span class="sxs-lookup"><span data-stu-id="815fb-140">System.Text</span></span>|<span data-ttu-id="815fb-141">Classi di testo.</span><span class="sxs-lookup"><span data-stu-id="815fb-141">Text classes.</span></span>|  
|<span data-ttu-id="815fb-142">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="815fb-142">System.Text.RegularExpressions</span></span>|<span data-ttu-id="815fb-143">Classi di espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="815fb-143">Regular expression classes.</span></span>|  
|<span data-ttu-id="815fb-144">System.Xml</span><span class="sxs-lookup"><span data-stu-id="815fb-144">System.Xml</span></span>|<span data-ttu-id="815fb-145">Classi XML di base.</span><span class="sxs-lookup"><span data-stu-id="815fb-145">Core XML classes.</span></span>|  
|<span data-ttu-id="815fb-146">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="815fb-146">System.Xml.Xsl</span></span>|<span data-ttu-id="815fb-147">Classi XSLT.</span><span class="sxs-lookup"><span data-stu-id="815fb-147">XSLT classes.</span></span>|  
|<span data-ttu-id="815fb-148">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="815fb-148">System.Xml.XPath</span></span>|<span data-ttu-id="815fb-149">Classi XPath (XML Path Language).</span><span class="sxs-lookup"><span data-stu-id="815fb-149">XML Path Language (XPath) classes.</span></span>|  
|<span data-ttu-id="815fb-150">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="815fb-150">Microsoft.VisualBasic</span></span>|<span data-ttu-id="815fb-151">Classi per gli script Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="815fb-151">Classes for Microsoft Visual Basic scripts.</span></span>|  
  
 <span data-ttu-id="815fb-152">Quando si dichiara una funzione, questa è contenuta in un blocco di script.</span><span class="sxs-lookup"><span data-stu-id="815fb-152">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="815fb-153">I fogli di stile possono contenere più blocchi di script con funzionamento indipendente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="815fb-153">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="815fb-154">Ciò significa che, all'interno di un blocco di script, non è possibile chiamare una funzione definita in un altro blocco di script a meno che per quest'ultimo non sia dichiarato lo stesso spazio dei nomi e lo stesso linguaggio di script.</span><span class="sxs-lookup"><span data-stu-id="815fb-154">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="815fb-155">Poiché ogni blocco di script può essere scritto nel proprio linguaggio e il blocco viene analizzato in base alle regole grammaticali del parser di quel linguaggio, è necessario usare la sintassi corretta per il linguaggio in uso.</span><span class="sxs-lookup"><span data-stu-id="815fb-155">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser, you must use the correct syntax for the language in use.</span></span> <span data-ttu-id="815fb-156">Ad esempio, in un blocco di script C# è un errore usare un nodo Comment XML `<!-- an XML comment -->` nel blocco.</span><span class="sxs-lookup"><span data-stu-id="815fb-156">For example, if you are in a C# script block, then it is an error to use an XML comment node `<!-- an XML comment -->` in the block.</span></span>  
  
 <span data-ttu-id="815fb-157">È necessario che gli argomenti forniti e i valori restituiti definiti dalle funzioni di script siano di tipo W3C (World Wide Web Consortium) XPath o XSLT.</span><span class="sxs-lookup"><span data-stu-id="815fb-157">The supplied arguments and return values defined by the script functions must be one of the World Wide Web Consortium (W3C) XPath or XSLT types.</span></span> <span data-ttu-id="815fb-158">Nella tabella seguente vengono mostrati i tipi W3C corrispondenti, le classi .NET Framework equivalenti (tipo) e se il tipo W3C è un tipo XPath o XSLT.</span><span class="sxs-lookup"><span data-stu-id="815fb-158">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (Type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="815fb-159">Type</span><span class="sxs-lookup"><span data-stu-id="815fb-159">Type</span></span>|<span data-ttu-id="815fb-160">Classe .NET Framework equivalente (tipo)</span><span class="sxs-lookup"><span data-stu-id="815fb-160">Equivalent .NET Framework Class (Type)</span></span>|<span data-ttu-id="815fb-161">Tipo XPath o tipo XSLT</span><span class="sxs-lookup"><span data-stu-id="815fb-161">XPath type or XSLT type</span></span>|  
|----------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="815fb-162">string</span><span class="sxs-lookup"><span data-stu-id="815fb-162">String</span></span>|<span data-ttu-id="815fb-163">System.String</span><span class="sxs-lookup"><span data-stu-id="815fb-163">System.String</span></span>|<span data-ttu-id="815fb-164">XPath</span><span class="sxs-lookup"><span data-stu-id="815fb-164">XPath</span></span>|  
|<span data-ttu-id="815fb-165">Boolean</span><span class="sxs-lookup"><span data-stu-id="815fb-165">Boolean</span></span>|<span data-ttu-id="815fb-166">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="815fb-166">System.Boolean</span></span>|<span data-ttu-id="815fb-167">XPath</span><span class="sxs-lookup"><span data-stu-id="815fb-167">XPath</span></span>|  
|<span data-ttu-id="815fb-168">Number</span><span class="sxs-lookup"><span data-stu-id="815fb-168">Number</span></span>|<span data-ttu-id="815fb-169">System.Double</span><span class="sxs-lookup"><span data-stu-id="815fb-169">System.Double</span></span>|<span data-ttu-id="815fb-170">XPath</span><span class="sxs-lookup"><span data-stu-id="815fb-170">XPath</span></span>|  
|<span data-ttu-id="815fb-171">Frammento di albero risultato</span><span class="sxs-lookup"><span data-stu-id="815fb-171">Result Tree Fragment</span></span>|<span data-ttu-id="815fb-172">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="815fb-172">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="815fb-173">XSLT</span><span class="sxs-lookup"><span data-stu-id="815fb-173">XSLT</span></span>|  
|<span data-ttu-id="815fb-174">Node set</span><span class="sxs-lookup"><span data-stu-id="815fb-174">Node Set</span></span>|<span data-ttu-id="815fb-175">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="815fb-175">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="815fb-176">XPath</span><span class="sxs-lookup"><span data-stu-id="815fb-176">XPath</span></span>|  
  
 <span data-ttu-id="815fb-177">Se la funzione di script usa un tipo numerico quale Int16, UInt16, Int32, UInt32, Int64, UInt64, Single o Decimal, questo verrà convertito in Double, che corrisponde al numero del tipo W3C XPath.</span><span class="sxs-lookup"><span data-stu-id="815fb-177">If the script function utilizes one of the following numeric types: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, or Decimal, they are forced to Double, which maps to the W3C XPath type number.</span></span> <span data-ttu-id="815fb-178">Tutti gli altri tipi verranno convertiti in stringhe usando il metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="815fb-178">All other types are forced to a string by calling the `ToString` method.</span></span>  
  
 <span data-ttu-id="815fb-179">Se la funzione di script usa un tipo diverso da quelli specificati in precedenza o se la funzione non viene compilata quando il foglio di stile viene caricato nell'oggetto <xref:System.Xml.Xsl.XslTransform>, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="815fb-179">If the script function utilizes a type other than the ones mentioned above, or if the function does not compile when the style sheet is loaded into the <xref:System.Xml.Xsl.XslTransform> object, an exception is thrown.</span></span>  
  
 <span data-ttu-id="815fb-180">Quando si usa l'elemento `msxsl:script`, si consiglia che tale script, indipendentemente dal linguaggio, venga inserito all'interno di una sezione CDATA.</span><span class="sxs-lookup"><span data-stu-id="815fb-180">When using the `msxsl:script` element, it is highly recommended that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="815fb-181">Nel codice XML seguente, ad esempio, viene illustrato il modello della sezione CDATA in cui è inserito il codice.</span><span class="sxs-lookup"><span data-stu-id="815fb-181">For example, the following XML shows the template of the CDATA section where your code is placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="815fb-182">Si consiglia di inserire tutto il contenuto dello script in una sezione CDATA, poiché è possibile che gli operatori, gli identificatori o i delimitatori per un determinato linguaggio vengano erroneamente interpretati come XML.</span><span class="sxs-lookup"><span data-stu-id="815fb-182">It is highly recommended that all script content be placed in a CDATA section, because operators, identifiers, or delimiters for a given language have the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="815fb-183">Nell'esempio seguente viene illustrato l'uso dell'operatore logico AND nello script.</span><span class="sxs-lookup"><span data-stu-id="815fb-183">The following example shows the use of the logical AND operator in script.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 <span data-ttu-id="815fb-184">In questo esempio viene generata un'eccezione in quanto le e commerciali non sono in sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="815fb-184">This throws an exception because the ampersands are not escaped.</span></span> <span data-ttu-id="815fb-185">Il documento viene caricato come XML e non viene applicato alcun trattamento speciale al testo compreso tra i tag dell'elemento `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="815fb-185">The document is loaded as XML, and no special treatment is applied to the text between the `msxsl:script` element tags.</span></span>  
  
## <a name="example"></a><span data-ttu-id="815fb-186">Esempio</span><span class="sxs-lookup"><span data-stu-id="815fb-186">Example</span></span>  
 <span data-ttu-id="815fb-187">Nell'esempio seguente viene usato uno script incorporato per calcolare la circonferenza di un cerchio di cui viene fornito il raggio.</span><span class="sxs-lookup"><span data-stu-id="815fb-187">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "calc.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XmlTextWriter to output to the console.
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
    writer.Formatting = Formatting.Indented  
  
    'Transform the file.  
    xslt.Transform(doc, Nothing, writer, Nothing)  
    writer.Close()  
  End Sub
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "calc.xsl";  
  
   public static void Main()  
   {  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XmlTextWriter to output to the console.
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting = Formatting.Indented;  
  
    //Transform the file.  
    xslt.Transform(doc, null, writer, null);  
    writer.Close();  
  }  
}  
```  
  
## <a name="input"></a><span data-ttu-id="815fb-188">Input</span><span class="sxs-lookup"><span data-stu-id="815fb-188">Input</span></span>  
 <span data-ttu-id="815fb-189">number.xml</span><span class="sxs-lookup"><span data-stu-id="815fb-189">number.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>  
```  
  
 <span data-ttu-id="815fb-190">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="815fb-190">calc.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
    xmlns:user="urn:my-scripts">  
  
  <msxsl:script language="C#" implements-prefix="user">  
     <![CDATA[  
     public double circumference(double radius)  
     {  
       double pi = 3.14;  
       double circ = pi*radius*2;  
       return circ;  
     }  
      ]]>  
   </msxsl:script>  
  
  <xsl:template match="data">
  <circles>  
  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="user:circumference(radius)"/>
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="815fb-191">Output</span><span class="sxs-lookup"><span data-stu-id="815fb-191">Output</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="815fb-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="815fb-192">See also</span></span>

- [<span data-ttu-id="815fb-193">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="815fb-193">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
