---
title: Cenni preliminari sul componente OpenFileDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3e5dc6630d9bc7a2090a28daabbf08eeed59005
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="fe3ef-102">Cenni preliminari sul componente OpenFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="fe3ef-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="fe3ef-103">Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="fe3ef-104">Ha lo stesso **Apri** la finestra di dialogo esposta dal sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="fe3ef-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="fe3ef-106">Utilizzando questo componente</span><span class="sxs-lookup"><span data-stu-id="fe3ef-106">Using this Component</span></span>  
 <span data-ttu-id="fe3ef-107">Utilizzare questo componente nell'applicazione basata su Windows come semplice soluzione per la selezione di file anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="fe3ef-108">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="fe3ef-109">Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.OpenFileDialog> componente, è necessario scrivere la propria logica per l'apertura di file.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="fe3ef-110">Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="fe3ef-111">È possibile consentire agli utenti di selezionare più file da aprire con il <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="fe3ef-112">Inoltre, è possibile utilizzare il <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> proprietà per determinare se una casella di controllo di sola lettura viene visualizzata nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="fe3ef-113">Il <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> proprietà indica se è selezionata la casella di controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="fe3ef-114">Infine, il <xref:System.Windows.Forms.FileDialog.Filter%2A> proprietà imposta la stringa filtro del nome file corrente, che determina le scelte visualizzate nella finestra di "tipo file" nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="fe3ef-115">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.OpenFileDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="fe3ef-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3ef-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe3ef-116">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="fe3ef-117">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="fe3ef-117">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
