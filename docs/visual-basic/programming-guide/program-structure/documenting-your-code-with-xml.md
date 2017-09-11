---
title: Documentazione del codice tramite XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0ce3f216f9e851feb0b3506b6ed1279b7d9479e7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="c6a8d-102">Documentazione del codice tramite XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6a8d-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="c6a8d-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], è possibile documentare il codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="c6a8d-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="c6a8d-104">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="c6a8d-104">XML Documentation Comments</span></span>  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c6a8d-105">fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-105"> provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="c6a8d-106">È possibile generare automaticamente uno scheletro XML per i tipi e membri e quindi fornire i riepiloghi, la documentazione descrittiva per ogni parametro e altre note.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="c6a8d-107">Con l'impostazione appropriata, la documentazione XML viene generata automaticamente in un file XML con lo stesso nome del progetto e l'estensione XML.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="c6a8d-108">Per ulteriori informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c6a8d-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="c6a8d-109">Il file XML può essere utilizzato o diversamente modificato come XML.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="c6a8d-110">Questo file si trova nella stessa directory del file di .exe o DLL di output del progetto.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="c6a8d-111">Documentazione XML inizia con `'''`.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="c6a8d-112">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="c6a8d-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="c6a8d-113">La documentazione deve essere ben formata XML.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="c6a8d-114">Se il codice XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento per informare che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="c6a8d-115">Gli sviluppatori sono liberi di creare il proprio set di tag.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="c6a8d-116">Esiste un set di tag (vedere "Sezioni correlate" in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="c6a8d-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="c6a8d-117">Alcuni dei tag consigliati hanno significati speciali:</span><span class="sxs-lookup"><span data-stu-id="c6a8d-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="c6a8d-118">Il \<param > tag viene utilizzato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="c6a8d-119">Se utilizzato, il compilatore verificherà che il parametro esista e che tutti i parametri sono descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="c6a8d-120">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="c6a8d-121">Il `cref` attributo può essere associato a qualsiasi tag per fornire un riferimento a un elemento di codice.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="c6a8d-122">Il compilatore verifica l'esistenza di questo elemento di codice.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="c6a8d-123">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="c6a8d-124">Il compilatore rispetta inoltre eventuali `Imports` istruzioni durante la ricerca di un tipo di `cref` attributo.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="c6a8d-125">Il \<riepilogo > tag viene usato da IntelliSense nel [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] per visualizzare informazioni aggiuntive su un tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="c6a8d-125">The \<summary> tag is used by IntelliSense in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c6a8d-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c6a8d-126">Related Sections</span></span>  
 <span data-ttu-id="c6a8d-127">Per informazioni dettagliate sulla creazione di un file XML con i commenti della documentazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6a8d-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c6a8d-128">/doc</span><span class="sxs-lookup"><span data-stu-id="c6a8d-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="c6a8d-129">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="c6a8d-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="c6a8d-130">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="c6a8d-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="c6a8d-131">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="c6a8d-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="c6a8d-132">Strumenti XML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6a8d-132">XML Tools in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="c6a8d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6a8d-133">See Also</span></span>  
 <span data-ttu-id="c6a8d-134">[Sviluppo di applicazioni con Visual Basic](../../../visual-basic/developing-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6a8d-134">[Developing Applications with Visual Basic](../../../visual-basic/developing-apps/index.md) </span></span>  
<span data-ttu-id="c6a8d-135"> [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="c6a8d-135"> [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)</span></span>
