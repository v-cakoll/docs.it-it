---
title: Output da un XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 178b1e949868d3af893cbcb6df63590053341a3e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710492"
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="4ba81-102">Output da un XslTransform</span><span class="sxs-lookup"><span data-stu-id="4ba81-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="4ba81-103">Poiché i fogli di stile consentono di determinare il formato di output usando un'istruzione `<xsl:output>` con l'attributo `method`, nella tabella seguente viene descritto il formato di output ottenuto quando si usa il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> per scrivere l'output e il formato dell'output è dichiarato come tipo <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="4ba81-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ba81-104">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="4ba81-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="4ba81-105">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="4ba81-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="4ba81-106">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="4ba81-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="4ba81-107">Poiché i fogli di stile consentono di determinare il formato di output usando un'istruzione `<xsl:output>` con l'attributo `method`, nella tabella seguente viene descritto il formato di output ottenuto quando si usa il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> per scrivere l'output e il formato dell'output è dichiarato come tipo <xref:System.IO.Stream> o <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="4ba81-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="4ba81-108">Nella tabella seguente viene descritto ciò che si verifica quando il tipo di output viene dichiarato dal metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> unitamente all'utilizzo di un'istruzione `<xsl:output>`.</span><span class="sxs-lookup"><span data-stu-id="4ba81-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="4ba81-109">\<xsl:output method = > attributo</span><span class="sxs-lookup"><span data-stu-id="4ba81-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="4ba81-110">Formato del risultato</span><span class="sxs-lookup"><span data-stu-id="4ba81-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="4ba81-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="4ba81-111">method="xml"</span></span>|<span data-ttu-id="4ba81-112">XML</span><span class="sxs-lookup"><span data-stu-id="4ba81-112">XML</span></span>|  
|<span data-ttu-id="4ba81-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="4ba81-113">method="html"</span></span>|<span data-ttu-id="4ba81-114">HTML</span><span class="sxs-lookup"><span data-stu-id="4ba81-114">HTML</span></span>|  
|<span data-ttu-id="4ba81-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="4ba81-115">method="text"</span></span>|<span data-ttu-id="4ba81-116">Testo</span><span class="sxs-lookup"><span data-stu-id="4ba81-116">Text</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="4ba81-117">Nota: quando l'output del metodo `<xsl:output>` è un oggetto <xref:System.Xml.Xsl.XslTransform.Transform%2A> o <xref:System.Xml.XmlReader>, l'istruzione <xref:System.Xml.XmlWriter> viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="4ba81-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="4ba81-118">Quando l'output del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> è di tipo <xref:System.IO.Stream> o <xref:System.IO.TextWriter>, sono supportati i seguenti attributi:</span><span class="sxs-lookup"><span data-stu-id="4ba81-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
- <span data-ttu-id="4ba81-119">encoding\*</span><span class="sxs-lookup"><span data-stu-id="4ba81-119">encoding\*</span></span>  
  
- <span data-ttu-id="4ba81-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="4ba81-120">omit-xml-declaration</span></span>  
  
- <span data-ttu-id="4ba81-121">standalone</span><span class="sxs-lookup"><span data-stu-id="4ba81-121">standalone</span></span>  
  
- <span data-ttu-id="4ba81-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="4ba81-122">doctype-public</span></span>  
  
- <span data-ttu-id="4ba81-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="4ba81-123">doctype-system</span></span>  
  
- <span data-ttu-id="4ba81-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="4ba81-124">cdata-section-elements</span></span>  
  
- <span data-ttu-id="4ba81-125">indent</span><span class="sxs-lookup"><span data-stu-id="4ba81-125">indent</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4ba81-126">\*L'attributo di codifica viene ignorato quando il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> invia l'output a un <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="4ba81-126">\*The encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="4ba81-127">Viene invece usata la proprietà di codifica del tipo <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="4ba81-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span> 
  
 <span data-ttu-id="4ba81-128">Quando l'output del metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> è un tipo <xref:System.IO.Stream>, l'attributo seguente viene ignorato:</span><span class="sxs-lookup"><span data-stu-id="4ba81-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
- <span data-ttu-id="4ba81-129">version: la versione è sempre 1.0</span><span class="sxs-lookup"><span data-stu-id="4ba81-129">version: the version is always 1.0</span></span>  
  
- <span data-ttu-id="4ba81-130">media-type: il tipo di supporto</span><span class="sxs-lookup"><span data-stu-id="4ba81-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="4ba81-131">Escape dei caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="4ba81-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="4ba81-132">Il tag `<xsl:text disable-output-escaping>` viene usato per indicare se deve essere eseguito o meno l'escape dei caratteri speciali in un formato XML (ad esempio, usando `<&lt>` anziché il simbolo `"<"`).</span><span class="sxs-lookup"><span data-stu-id="4ba81-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="4ba81-133">L'attributo `disable-output-escaping` viene ignorato durante la trasformazione in un oggetto <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter> e non influisce sui caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="4ba81-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba81-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ba81-134">See also</span></span>

- [<span data-ttu-id="4ba81-135">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="4ba81-135">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
