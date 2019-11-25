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
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976996"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b1604-102">Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b1604-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="b1604-103">Nelle finestre di dialogo predefinite Apri e Salva in Windows Vista è presente un'area sul lato sinistro della finestra di dialogo denominata **collegamenti preferiti**.</span><span class="sxs-lookup"><span data-stu-id="b1604-103">The default open and save dialog boxes on Windows Vista have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="b1604-104">che contiene percorsi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b1604-104">This area is called custom places.</span></span> <span data-ttu-id="b1604-105">Le classi <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> consentono di aggiungere cartelle alla raccolta di <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1604-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1604-106">Affinché una posizione personalizzata venga visualizzata nella <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, la proprietà <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> deve essere impostata su `true` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="b1604-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b1604-107">Per aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b1604-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="b1604-108">Aggiungere un percorso, un GUID della cartella nota o un oggetto <xref:System.Windows.Forms.FileDialogCustomPlace> alla raccolta <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b1604-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="b1604-109">L'esempio di codice riportato di seguito illustra come aggiungere un percorso:</span><span class="sxs-lookup"><span data-stu-id="b1604-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b1604-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1604-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b1604-111">GUID di cartella nota per percorsi personalizzati della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b1604-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
