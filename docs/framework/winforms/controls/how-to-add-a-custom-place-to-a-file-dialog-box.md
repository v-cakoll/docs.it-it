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
ms.openlocfilehash: 7a6ace385f7594a467785fbc677517c8a6e1ab53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525739"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File
Le finestre di dialogo predefinite Apri e Salva in [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] dispongono di un'area sul lato sinistro della finestra di dialogo denominata **Collegamenti preferiti**, che contiene percorsi personalizzati. Il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi consentono di aggiungere cartelle per il <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> insieme.  
  
> [!NOTE]
>  Affinché un percorso personalizzato venga visualizzato nel <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà deve essere impostata su `true` (impostazione predefinita).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Per aggiungere un percorso personalizzato a una finestra di dialogo File  
  
-   Aggiungere un percorso, un GUID di cartella nota o un <xref:System.Windows.Forms.FileDialogCustomPlace> dell'oggetto per il <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta nella finestra di dialogo.  
  
     L'esempio di codice riportato di seguito illustra come aggiungere un percorso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [GUID di cartella nota per percorsi personalizzati della finestra di dialogo File](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
