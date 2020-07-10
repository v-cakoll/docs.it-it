---
title: 'Procedura: stampare un Windows Form'
description: Informazioni su come stampare una copia del Windows Form corrente a livello di codice usando il metodo CopyFromScreen.
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
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174692"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="8ed7c-103">Procedura: stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ed7c-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="8ed7c-104">Come parte del processo di sviluppo, in genere si desidera stampare una copia di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8ed7c-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="8ed7c-105">Nell'esempio di codice riportato di seguito viene illustrato come stampare una copia del form corrente utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8ed7c-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ed7c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ed7c-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8ed7c-107">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="8ed7c-107">Robust Programming</span></span>  
 <span data-ttu-id="8ed7c-108">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="8ed7c-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8ed7c-109">Non si dispone delle autorizzazioni necessarie per accedere alla stampante.</span><span class="sxs-lookup"><span data-stu-id="8ed7c-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="8ed7c-110">Nessuna stampante installata.</span><span class="sxs-lookup"><span data-stu-id="8ed7c-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8ed7c-111">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8ed7c-111">.NET Framework Security</span></span>  
 <span data-ttu-id="8ed7c-112">Per eseguire questo esempio di codice, è necessario disporre dell'autorizzazione per accedere alla stampante utilizzata con il computer.</span><span class="sxs-lookup"><span data-stu-id="8ed7c-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed7c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ed7c-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="8ed7c-114">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="8ed7c-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="8ed7c-115">Procedura: stampare grafica in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ed7c-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
