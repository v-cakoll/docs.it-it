---
title: Documentazione del codice tramite XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 324519248b90d4f61e67803a10b3cd6c566a2a04
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404862"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="8c173-102">Documentazione del codice tramite XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c173-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="8c173-103">In Visual Basic è possibile documentare il codice usando XML</span><span class="sxs-lookup"><span data-stu-id="8c173-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="8c173-104">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="8c173-104">XML Documentation Comments</span></span>

<span data-ttu-id="8c173-105">Visual Basic fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti.</span><span class="sxs-lookup"><span data-stu-id="8c173-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="8c173-106">È possibile generare automaticamente uno scheletro XML per i tipi e i membri, quindi fornire riepiloghi, documentazione descrittiva per ogni parametro e altre osservazioni.</span><span class="sxs-lookup"><span data-stu-id="8c173-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="8c173-107">Con la configurazione appropriata, la documentazione XML viene emessa automaticamente in un file XML con lo stesso nome del progetto e dell'estensione XML.</span><span class="sxs-lookup"><span data-stu-id="8c173-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="8c173-108">Per ulteriori informazioni, vedere [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="8c173-108">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="8c173-109">Il file XML può essere utilizzato o modificato in altro modo come XML.</span><span class="sxs-lookup"><span data-stu-id="8c173-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="8c173-110">Questo file si trova nella stessa directory del file con estensione exe o dll di output del progetto.</span><span class="sxs-lookup"><span data-stu-id="8c173-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="8c173-111">La documentazione XML inizia con `'''` .</span><span class="sxs-lookup"><span data-stu-id="8c173-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="8c173-112">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="8c173-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="8c173-113">La documentazione deve essere in codice XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="8c173-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="8c173-114">Se il formato XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento che informa che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="8c173-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="8c173-115">Gli sviluppatori sono liberi di creare set di tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8c173-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="8c173-116">È disponibile un set di tag consigliato (vedere "sezioni correlate" in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="8c173-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="8c173-117">Alcuni tag consigliati hanno un significato speciale:</span><span class="sxs-lookup"><span data-stu-id="8c173-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="8c173-118">Il \<param> tag viene usato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="8c173-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="8c173-119">Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="8c173-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="8c173-120">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="8c173-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="8c173-121">L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="8c173-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="8c173-122">Il compilatore verifica l'esistenza di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="8c173-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="8c173-123">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="8c173-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="8c173-124">Il compilatore rispetta anche le `Imports` istruzioni quando si cerca un tipo descritto nell' `cref` attributo.</span><span class="sxs-lookup"><span data-stu-id="8c173-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="8c173-125">Il \<summary> tag viene usato da IntelliSense in Visual Studio per visualizzare informazioni aggiuntive su un tipo o un membro.</span><span class="sxs-lookup"><span data-stu-id="8c173-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8c173-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8c173-126">Related Sections</span></span>

<span data-ttu-id="8c173-127">Per informazioni dettagliate sulla creazione di un file XML con i commenti relativi alla documentazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c173-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="8c173-128">-doc</span><span class="sxs-lookup"><span data-stu-id="8c173-128">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="8c173-129">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="8c173-129">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="8c173-130">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="8c173-130">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="8c173-131">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="8c173-131">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="8c173-132">Strumenti XML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8c173-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="8c173-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c173-133">See also</span></span>

- [<span data-ttu-id="8c173-134">Sviluppo di applicazioni con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c173-134">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="8c173-135">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c173-135">Visual Basic Programming Guide</span></span>](../index.md)
