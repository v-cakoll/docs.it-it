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
ms.openlocfilehash: d9c1373a16f7d62c2933e01e513478fc6c9866d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721879"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b18c0-102">Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b18c0-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="b18c0-103">Le finestre di dialogo predefinite Apri e Salva in [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] dispongono di un'area sul lato sinistro della finestra di dialogo denominata **Collegamenti preferiti**,</span><span class="sxs-lookup"><span data-stu-id="b18c0-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="b18c0-104">che contiene percorsi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b18c0-104">This area is called custom places.</span></span> <span data-ttu-id="b18c0-105">Il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi consentono di aggiungere cartelle al <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="b18c0-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b18c0-106">Affinché un percorso personalizzato venga visualizzato nel <xref:System.Windows.Forms.OpenFileDialog> oppure <xref:System.Windows.Forms.SaveFileDialog>, il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà deve essere impostata su `true` (predefinito).</span><span class="sxs-lookup"><span data-stu-id="b18c0-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="b18c0-107">Per aggiungere un percorso personalizzato a una finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b18c0-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="b18c0-108">Aggiungere un percorso, un GUID della cartella nota, o un <xref:System.Windows.Forms.FileDialogCustomPlace> dell'oggetto per il <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b18c0-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="b18c0-109">L'esempio di codice riportato di seguito illustra come aggiungere un percorso:</span><span class="sxs-lookup"><span data-stu-id="b18c0-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b18c0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b18c0-110">See also</span></span>
- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b18c0-111">GUID di cartella nota per percorsi personalizzati della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="b18c0-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
