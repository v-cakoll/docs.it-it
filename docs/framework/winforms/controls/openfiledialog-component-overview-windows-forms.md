---
title: Cenni preliminari sul componente OpenFileDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211711"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="edc6d-102">Cenni preliminari sul componente OpenFileDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="edc6d-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="edc6d-103">Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="edc6d-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="edc6d-104">È uguale **Apri File** nella finestra di dialogo esposta dal sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="edc6d-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="edc6d-105">Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="edc6d-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="edc6d-106">Utilizzare questo componente</span><span class="sxs-lookup"><span data-stu-id="edc6d-106">Use this component</span></span>

<span data-ttu-id="edc6d-107">Utilizzare questo componente all'interno dell'applicazione basata su Windows come una soluzione semplice per la selezione di file anziché configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="edc6d-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="edc6d-108">Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.</span><span class="sxs-lookup"><span data-stu-id="edc6d-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="edc6d-109">Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.OpenFileDialog> componente, è necessario scrivere la propria logica di apertura di file.</span><span class="sxs-lookup"><span data-stu-id="edc6d-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="edc6d-110">Usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="edc6d-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="edc6d-111">È possibile abilitare gli utenti di selezionare più file da aprire con il <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="edc6d-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="edc6d-112">Inoltre, è possibile usare il <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> proprietà per determinare se una casella di controllo di sola lettura viene visualizzato nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="edc6d-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="edc6d-113">Il <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> proprietà indica se è selezionata la casella di controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="edc6d-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="edc6d-114">Infine, il <xref:System.Windows.Forms.FileDialog.Filter%2A> proprietà imposta la stringa filtro, nome di file corrente che determina le scelte visualizzate nella finestra di "File di tipo" nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="edc6d-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="edc6d-115">Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.OpenFileDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="edc6d-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="edc6d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edc6d-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="edc6d-117">Componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="edc6d-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
