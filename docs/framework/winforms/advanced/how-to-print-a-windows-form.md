---
title: 'Procedura: Stampare un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 85fb12028687578b76e0f16061deb9b9a4de70e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003977"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="ba7f5-102">Procedura: Stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba7f5-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="ba7f5-103">Come parte del processo di sviluppo, è in genere opportuno stampare una copia di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="ba7f5-104">Esempio di codice seguente viene illustrato come stampare una copia del modulo corrente usando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="ba7f5-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba7f5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba7f5-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ba7f5-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ba7f5-106">Compiling the Code</span></span>  
 <span data-ttu-id="ba7f5-107">Questo è un esempio di codice completo che contiene un `Main` (metodo).</span><span class="sxs-lookup"><span data-stu-id="ba7f5-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ba7f5-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ba7f5-108">Robust Programming</span></span>  
 <span data-ttu-id="ba7f5-109">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="ba7f5-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ba7f5-110">Non hai le autorizzazioni per accedere alla stampante.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-110">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="ba7f5-111">Non è installata alcuna stampante.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ba7f5-112">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ba7f5-112">.NET Framework Security</span></span>  
 <span data-ttu-id="ba7f5-113">Per eseguire questo esempio di codice, è necessario disporre dell'autorizzazione per accedere alla stampante utilizzata con il computer.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7f5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba7f5-114">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="ba7f5-115">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="ba7f5-115">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="ba7f5-116">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba7f5-116">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
