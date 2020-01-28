---
title: "Procedura: estrarre l'icona associata a un file"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742548"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="76cf5-102">Procedura: estrarre l'icona associata a un file in Windows Form</span><span class="sxs-lookup"><span data-stu-id="76cf5-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="76cf5-103">Molti file hanno icone incorporate che forniscono una rappresentazione visiva del tipo di file associato.</span><span class="sxs-lookup"><span data-stu-id="76cf5-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="76cf5-104">Ad esempio, i documenti di Microsoft Word contengono un'icona che li identifica come documenti di Word.</span><span class="sxs-lookup"><span data-stu-id="76cf5-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="76cf5-105">Quando si visualizzano i file in un controllo elenco o in un controllo tabella, potrebbe essere necessario visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome file.</span><span class="sxs-lookup"><span data-stu-id="76cf5-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="76cf5-106">Questa operazione può essere eseguita facilmente usando il metodo <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="76cf5-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76cf5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="76cf5-107">Example</span></span>  
 <span data-ttu-id="76cf5-108">Nell'esempio di codice riportato di seguito viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="76cf5-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="76cf5-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="76cf5-109">Compiling the Code</span></span>  
 <span data-ttu-id="76cf5-110">Per compilare l'esempio:</span><span class="sxs-lookup"><span data-stu-id="76cf5-110">To compile the example:</span></span>  
  
- <span data-ttu-id="76cf5-111">Incollare il codice precedente in un Windows Form e chiamare il metodo `ExtractAssociatedIconExample` dal costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="76cf5-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="76cf5-112">Sarà necessario assicurarsi che il form importi lo spazio dei nomi <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="76cf5-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cf5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76cf5-113">See also</span></span>

- [<span data-ttu-id="76cf5-114">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="76cf5-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="76cf5-115">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="76cf5-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
