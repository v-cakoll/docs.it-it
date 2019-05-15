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
ms.openlocfilehash: cd10e0a43ff37b921dc8e024d7a6a51fafbb0400
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591847"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="52092-102">Procedura: Stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="52092-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="52092-103">Come parte del processo di sviluppo, è in genere opportuno stampare una copia di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="52092-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="52092-104">Esempio di codice seguente viene illustrato come stampare una copia del modulo corrente usando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="52092-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52092-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="52092-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="52092-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="52092-106">Robust Programming</span></span>  
 <span data-ttu-id="52092-107">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="52092-107">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="52092-108">Non hai le autorizzazioni per accedere alla stampante.</span><span class="sxs-lookup"><span data-stu-id="52092-108">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="52092-109">Non è installata alcuna stampante.</span><span class="sxs-lookup"><span data-stu-id="52092-109">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="52092-110">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="52092-110">.NET Framework Security</span></span>  
 <span data-ttu-id="52092-111">Per eseguire questo esempio di codice, è necessario disporre dell'autorizzazione per accedere alla stampante utilizzata con il computer.</span><span class="sxs-lookup"><span data-stu-id="52092-111">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52092-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52092-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="52092-113">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="52092-113">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="52092-114">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="52092-114">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
