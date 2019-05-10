---
title: "Procedura: Estrarre l'icona associata a un file in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: c3173a3fa756a3294154217f5cf0a13dbc8721f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645406"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="80810-102">Procedura: Estrarre l'icona associata a un file in Windows Form</span><span class="sxs-lookup"><span data-stu-id="80810-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="80810-103">Numero di file è incorporati icone che forniscono una rappresentazione visiva del tipo di file associato.</span><span class="sxs-lookup"><span data-stu-id="80810-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="80810-104">Documenti di Microsoft Word, ad esempio, contengono un'icona che li identifica come documenti di Word.</span><span class="sxs-lookup"><span data-stu-id="80810-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="80810-105">Quando si visualizzano i file in un controllo di elenco o tabella, è possibile visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome di file.</span><span class="sxs-lookup"><span data-stu-id="80810-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="80810-106">È possibile farlo facilmente usando le <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80810-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80810-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="80810-107">Example</span></span>  
 <span data-ttu-id="80810-108">Esempio di codice seguente viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="80810-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80810-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="80810-109">Compiling the Code</span></span>  
 <span data-ttu-id="80810-110">Per compilare l'esempio:</span><span class="sxs-lookup"><span data-stu-id="80810-110">To compile the example:</span></span>  
  
- <span data-ttu-id="80810-111">Incollare il codice precedente in un Windows Form e chiamare il `ExtractAssociatedIconExample` metodo dal costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="80810-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="80810-112">È necessario assicurarsi che il modulo Importa la <xref:System.IO> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="80810-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80810-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80810-113">See also</span></span>

- [<span data-ttu-id="80810-114">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="80810-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="80810-115">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="80810-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
