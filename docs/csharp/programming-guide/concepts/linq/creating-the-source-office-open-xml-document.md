---
title: Creazione del documento Office Open XML di origine (C#)
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: d6c4d8866bba58e86735099a62041894a9faa9b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204162"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="cdcd0-102">Creazione del documento Office Open XML di origine (C#)</span><span class="sxs-lookup"><span data-stu-id="cdcd0-102">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="cdcd0-103">In questo argomento viene illustrato come creare il documento WordprocessingML di Office Open XML usato in altri esempi di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="cdcd0-104">Seguendo queste istruzioni, l'output ottenuto sarà uguale a quello indicato in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-104">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="cdcd0-105">Tuttavia, gli esempi presentati in questa esercitazione funzioneranno con qualsiasi documento WordprocessingML valido.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="cdcd0-106">Per creare il documento usato in questa esercitazione, è necessario che nel computer sia installato Microsoft Office 2007 o versione successiva oppure Microsoft Office 2003 con il pacchetto di compatibilità per Microsoft Office per i formati di file Word, Excel e PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="cdcd0-107">Creazione del documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="cdcd0-107">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="cdcd0-108">Per creare il documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="cdcd0-108">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="cdcd0-109">Creare un nuovo documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-109">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="cdcd0-110">Incollare il testo seguente nel nuovo documento:</span><span class="sxs-lookup"><span data-stu-id="cdcd0-110">Paste the following text into the new document:</span></span>

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

3. <span data-ttu-id="cdcd0-111">Formattare la prima riga con lo stile "Intestazione 1".</span><span class="sxs-lookup"><span data-stu-id="cdcd0-111">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="cdcd0-112">Selezionare le righe contenenti codice C#.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="cdcd0-113">La prima riga inizia con la parola chiave `using`.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="cdcd0-114">L'ultima riga corrisponde all'ultima parentesi graffa di chiusura.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-114">The last line is the last closing brace.</span></span> <span data-ttu-id="cdcd0-115">Formattare le righe con il tipo di carattere Courier.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-115">Format the lines with the courier font.</span></span> <span data-ttu-id="cdcd0-116">Formattarle con un nuovo stile, da denominare "Code".</span><span class="sxs-lookup"><span data-stu-id="cdcd0-116">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="cdcd0-117">Infine, selezionare l'intera riga che contiene l'output e formattarla con lo stile `Code`.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="cdcd0-118">Salvare il documento e denominarlo SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-118">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdcd0-119">Se si usa Microsoft Word 2003, selezionare **Documento di Word 2007** nell'elenco a discesa **Tipo file**.</span><span class="sxs-lookup"><span data-stu-id="cdcd0-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
