---
title: Creazione del documento Office Open XML di origine (C#)
description: Creare un documento WordprocessingML di Office Open XML da usare con le esercitazioni su C#. Questo articolo richiede Microsoft Office.
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: e6d6908ee6560218793454f3871705e74095f543
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103999"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="ace2a-104">Creazione del documento Office Open XML di origine (C#)</span><span class="sxs-lookup"><span data-stu-id="ace2a-104">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="ace2a-105">In questo argomento viene illustrato come creare il documento WordprocessingML di Office Open XML usato in altri esempi di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ace2a-105">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="ace2a-106">Seguendo queste istruzioni, l'output ottenuto sarà uguale a quello indicato in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="ace2a-106">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="ace2a-107">Tuttavia, gli esempi presentati in questa esercitazione funzioneranno con qualsiasi documento WordprocessingML valido.</span><span class="sxs-lookup"><span data-stu-id="ace2a-107">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="ace2a-108">Per creare il documento usato in questa esercitazione, è necessario che nel computer sia installato Microsoft Office 2007 o versione successiva oppure Microsoft Office 2003 con il pacchetto di compatibilità per Microsoft Office per i formati di file Word, Excel e PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="ace2a-108">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="ace2a-109">Creazione del documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="ace2a-109">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="ace2a-110">Per creare il documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="ace2a-110">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="ace2a-111">Creare un nuovo documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="ace2a-111">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="ace2a-112">Incollare il testo seguente nel nuovo documento:</span><span class="sxs-lookup"><span data-stu-id="ace2a-112">Paste the following text into the new document:</span></span>

    ```text
    Parsing WordprocessingML with LINQ to XML

    The following example prints to the console.

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. <span data-ttu-id="ace2a-113">Formattare la prima riga con lo stile "Intestazione 1".</span><span class="sxs-lookup"><span data-stu-id="ace2a-113">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="ace2a-114">Selezionare le righe contenenti codice C#.</span><span class="sxs-lookup"><span data-stu-id="ace2a-114">Select the lines that contain the C# code.</span></span> <span data-ttu-id="ace2a-115">La prima riga inizia con la parola chiave `using`.</span><span class="sxs-lookup"><span data-stu-id="ace2a-115">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="ace2a-116">L'ultima riga corrisponde all'ultima parentesi graffa di chiusura.</span><span class="sxs-lookup"><span data-stu-id="ace2a-116">The last line is the last closing brace.</span></span> <span data-ttu-id="ace2a-117">Formattare le righe con il tipo di carattere Courier.</span><span class="sxs-lookup"><span data-stu-id="ace2a-117">Format the lines with the courier font.</span></span> <span data-ttu-id="ace2a-118">Formattarle con un nuovo stile, da denominare "Code".</span><span class="sxs-lookup"><span data-stu-id="ace2a-118">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="ace2a-119">Infine, selezionare l'intera riga che contiene l'output e formattarla con lo stile `Code`.</span><span class="sxs-lookup"><span data-stu-id="ace2a-119">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="ace2a-120">Salvare il documento e denominarlo SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="ace2a-120">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ace2a-121">Se si usa Microsoft Word 2003, selezionare **Documento di Word 2007** nell'elenco a discesa **Tipo file**.</span><span class="sxs-lookup"><span data-stu-id="ace2a-121">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
