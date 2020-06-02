---
title: Utilizzo della classe XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 8705b4c6324ce20a1f37d3ee864ab494adcdd6a5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281770"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="88f82-102">Utilizzo della classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="88f82-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="88f82-103">La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT di Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88f82-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="88f82-104">Questa classe consente di compilare fogli di stile e di eseguire trasformazioni XSLT.</span><span class="sxs-lookup"><span data-stu-id="88f82-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88f82-105">Sebbene le prestazioni complessive della classe <xref:System.Xml.Xsl.XslCompiledTransform> siano migliori rispetto alla classe <xref:System.Xml.Xsl.XslTransform>, l'esecuzione del metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslCompiledTransform> potrebbe risultare più lenta di quella del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslTransform> la prima volta che tale metodo viene chiamato su una trasformazione.</span><span class="sxs-lookup"><span data-stu-id="88f82-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="88f82-106">Questa situazione si verifica perché il file XSLT deve essere compilato prima del caricamento.</span><span class="sxs-lookup"><span data-stu-id="88f82-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="88f82-107">Per altre informazioni, vedere il post di blog seguente: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (XslCompiledTransform è più lento di XslTransform?)</span><span class="sxs-lookup"><span data-stu-id="88f82-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88f82-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="88f82-108">In This Section</span></span>  
 [<span data-ttu-id="88f82-109">Input alla classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="88f82-109">Inputs to the XslCompiledTransform Class</span></span>](inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="88f82-110">Vengono descritte le opzioni di input XSLT disponibili.</span><span class="sxs-lookup"><span data-stu-id="88f82-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="88f82-111">Opzioni di output nella classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="88f82-111">Output Options on the XslCompiledTransform Class</span></span>](output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="88f82-112">Vengono descritte le opzioni di output XSLT disponibili.</span><span class="sxs-lookup"><span data-stu-id="88f82-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="88f82-113">Risoluzione delle risorse esterne durante l'elaborazione XSLT</span><span class="sxs-lookup"><span data-stu-id="88f82-113">Resolving External Resources During XSLT Processing</span></span>](resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="88f82-114">Viene descritto come usare la classe <xref:System.Xml.XmlResolver> per risolvere risorse esterne.</span><span class="sxs-lookup"><span data-stu-id="88f82-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="88f82-115">Estensione di fogli di stile XSLT</span><span class="sxs-lookup"><span data-stu-id="88f82-115">Extending XSLT Style Sheets</span></span>](extending-xslt-style-sheets.md)  
 <span data-ttu-id="88f82-116">Viene descritto il supporto delle estensioni XSLT.</span><span class="sxs-lookup"><span data-stu-id="88f82-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="88f82-117">Errori XSLT risolvibili</span><span class="sxs-lookup"><span data-stu-id="88f82-117">Recoverable XSLT Errors</span></span>](recoverable-xslt-errors.md)|<span data-ttu-id="88f82-118">Vengono elencati i comportamenti discretionary consentiti dalla raccomandazione W3C (World Wide Web Consortium) XSLT 1.0 e viene descritto il modo in cui tali comportamenti vengono gestiti dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="88f82-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="88f82-119">Procedura: Trasformare un frammento di nodo</span><span class="sxs-lookup"><span data-stu-id="88f82-119">How to: Transform a Node Fragment</span></span>](how-to-transform-a-node-fragment.md)|<span data-ttu-id="88f82-120">Viene descritto come trasformare un frammento di nodo.</span><span class="sxs-lookup"><span data-stu-id="88f82-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="88f82-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="88f82-121">Related Sections</span></span>  
 [<span data-ttu-id="88f82-122">Migrazione dalla classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="88f82-122">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="88f82-123">Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="88f82-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f82-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88f82-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
