---
title: 'Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 797b98cb408c7f9fc1d55b774f7ceccef009bb22
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674648"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="e9aa4-102">Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="e9aa4-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="e9aa4-103">Le finestre di dialogo predefinite Apri e Salva in [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] dispongono di un'area sul lato sinistro della finestra di dialogo denominata **Collegamenti preferiti**,</span><span class="sxs-lookup"><span data-stu-id="e9aa4-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="e9aa4-104">che contiene percorsi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e9aa4-104">This area is called custom places.</span></span> <span data-ttu-id="e9aa4-105">Il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi consentono di aggiungere cartelle al <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="e9aa4-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9aa4-106">Affinché un percorso personalizzato venga visualizzato nel <xref:System.Windows.Forms.OpenFileDialog> oppure <xref:System.Windows.Forms.SaveFileDialog>, il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà deve essere impostata su `true` (predefinito).</span><span class="sxs-lookup"><span data-stu-id="e9aa4-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="e9aa4-107">Per aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="e9aa4-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="e9aa4-108">Aggiungere un percorso, un GUID della cartella nota, o un <xref:System.Windows.Forms.FileDialogCustomPlace> dell'oggetto per il <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e9aa4-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="e9aa4-109">L'esempio di codice riportato di seguito illustra come aggiungere un percorso:</span><span class="sxs-lookup"><span data-stu-id="e9aa4-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e9aa4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9aa4-110">See also</span></span>
- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e9aa4-111">GUID di cartella nota per percorsi personalizzati della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="e9aa4-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
