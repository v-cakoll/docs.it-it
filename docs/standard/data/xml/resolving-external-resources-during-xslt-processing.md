---
title: Risoluzione delle risorse esterne durante l'elaborazione XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 58407d5f0c6e602af15f5b19b9a19cc6379b9af7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710284"
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="2f851-102">Risoluzione delle risorse esterne durante l'elaborazione XSLT</span><span class="sxs-lookup"><span data-stu-id="2f851-102">Resolving External Resources During XSLT Processing</span></span>
<span data-ttu-id="2f851-103">Durante una trasformazione XSLT si presentano vari casi in cui può essere necessario risolvere le risorse esterne.</span><span class="sxs-lookup"><span data-stu-id="2f851-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="2f851-104">Utilizzo della classe XmlResolver</span><span class="sxs-lookup"><span data-stu-id="2f851-104">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="2f851-105">La classe <xref:System.Xml.XmlResolver> viene usata per risolvere risorse esterne.</span><span class="sxs-lookup"><span data-stu-id="2f851-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="2f851-106">Nella tabella seguente vengono descritti i casi in cui il tipo <xref:System.Xml.XmlResolver> viene interessato dall'elaborazione XSLT.</span><span class="sxs-lookup"><span data-stu-id="2f851-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="2f851-107">Attività XSLT</span><span class="sxs-lookup"><span data-stu-id="2f851-107">XSLT task</span></span>|<span data-ttu-id="2f851-108">Scopo per il quale viene usato XmlResolver</span><span class="sxs-lookup"><span data-stu-id="2f851-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="2f851-109">Compilare il foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="2f851-109">Compile the style sheet.</span></span>|<span data-ttu-id="2f851-110">Risolvere l'URI del foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="2f851-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="2f851-111">e</span><span class="sxs-lookup"><span data-stu-id="2f851-111">-and-</span></span><br /><br /> <span data-ttu-id="2f851-112">Risolvere i riferimenti URI negli elementi `xsl:import` o `xsl:include`.</span><span class="sxs-lookup"><span data-stu-id="2f851-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="2f851-113">Eseguire il foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="2f851-113">Execute the style sheet.</span></span>|<span data-ttu-id="2f851-114">Risolvere l'URI del documento di contesto.</span><span class="sxs-lookup"><span data-stu-id="2f851-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="2f851-115">e</span><span class="sxs-lookup"><span data-stu-id="2f851-115">-and-</span></span><br /><br /> <span data-ttu-id="2f851-116">Risolvere i riferimenti URI in qualsiasi funzione `document()` XSLT.</span><span class="sxs-lookup"><span data-stu-id="2f851-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="2f851-117">I metodi <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> e <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> includono overload che accettano un oggetto <xref:System.Xml.XmlResolver> come argomento.</span><span class="sxs-lookup"><span data-stu-id="2f851-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="2f851-118">Se non viene specificato alcun tipo <xref:System.Xml.XmlResolver>, viene usato un tipo predefinito <xref:System.Xml.XmlUrlResolver> senza credenziali.</span><span class="sxs-lookup"><span data-stu-id="2f851-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="2f851-119">Nell'elenco seguente viene descritto quando può essere necessario specificare un oggetto <xref:System.Xml.XmlResolver>:</span><span class="sxs-lookup"><span data-stu-id="2f851-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
- <span data-ttu-id="2f851-120">Se il processo XSLT richiede l'accesso a una risorsa di rete che richiede l'autenticazione, è possibile usare un tipo <xref:System.Xml.XmlResolver> con le credenziali necessarie.</span><span class="sxs-lookup"><span data-stu-id="2f851-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
- <span data-ttu-id="2f851-121">Se si desidera limitare le risorse a cui può accedere il processo XSLT, è possibile usare un <xref:System.Xml.XmlSecureResolver> con il set di autorizzazioni corretto.</span><span class="sxs-lookup"><span data-stu-id="2f851-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="2f851-122">Usare la classe <xref:System.Xml.XmlSecureResolver> se è necessario aprire una risorsa che non si controlla o che non è considerata affidabile.</span><span class="sxs-lookup"><span data-stu-id="2f851-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
- <span data-ttu-id="2f851-123">Se si desidera personalizzare il comportamento, è possibile implementare la propria classe <xref:System.Xml.XmlResolver> e usarla per risolvere le risorse.</span><span class="sxs-lookup"><span data-stu-id="2f851-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
- <span data-ttu-id="2f851-124">Se si desidera assicurarsi che non venga eseguito l'accesso ad alcuna risorsa esterna, è possibile specificare `null` per l'argomento <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="2f851-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f851-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f851-125">Example</span></span>  
 <span data-ttu-id="2f851-126">Nell'esempio seguente viene compilato un foglio di stile archiviato su una risorsa di rete.</span><span class="sxs-lookup"><span data-stu-id="2f851-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="2f851-127">Un oggetto <xref:System.Xml.XmlUrlResolver> specificherà le credenziali necessarie per accedere al foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="2f851-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="2f851-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f851-128">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [<span data-ttu-id="2f851-129">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="2f851-129">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
