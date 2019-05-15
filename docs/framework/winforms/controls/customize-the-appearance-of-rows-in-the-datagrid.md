---
title: "Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: f7dcb3d949182efee3538174909b0f856dceedee
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589482"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="39dbe-102">Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39dbe-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="39dbe-103">È possibile controllare l'aspetto delle righe <xref:System.Windows.Forms.DataGridView> mediante la gestione di uno degli eventi o entrambi gli eventi <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39dbe-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="39dbe-104">Questi eventi sono stati progettati in modo che l'utente possa disegnare solo ciò che vuole e lasciare che il controllo <xref:System.Windows.Forms.DataGridView> disegni il resto.</span><span class="sxs-lookup"><span data-stu-id="39dbe-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="39dbe-105">Ad esempio, se si vuole disegnare uno sfondo personalizzato, è possibile gestire l'evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> e lasciare che le singole celle disegnino il contenuto in primo piano.</span><span class="sxs-lookup"><span data-stu-id="39dbe-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="39dbe-106">In alternativa è possibile lasciare che le celle si disegnino da sole e aggiungere il contenuto in primo piano in un gestore per l'evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39dbe-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="39dbe-107">È anche possibile disabilitare il disegno delle celle e disegnare tutto personalmente in un gestore dell'evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39dbe-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="39dbe-108">Nell'esempio di codice seguente i gestori vengono implementati per entrambi gli eventi in modo da fornire uno sfondo con sfumature selezionabili e un contenuto in primo piano personalizzato che si estende su più colonne.</span><span class="sxs-lookup"><span data-stu-id="39dbe-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39dbe-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="39dbe-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="39dbe-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="39dbe-110">Compiling the Code</span></span>  
 <span data-ttu-id="39dbe-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="39dbe-111">This example requires:</span></span>  
  
- <span data-ttu-id="39dbe-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="39dbe-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dbe-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39dbe-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="39dbe-114">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="39dbe-114">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="39dbe-115">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="39dbe-115">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
