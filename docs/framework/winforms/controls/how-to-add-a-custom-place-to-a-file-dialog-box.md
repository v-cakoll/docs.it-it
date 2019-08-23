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
ms.openlocfilehash: 824c948fafd0a0995ad261389414d2d79918c8a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916342"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File
Le finestre di dialogo predefinite Apri e Salva in [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] dispongono di un'area sul lato sinistro della finestra di dialogo denominata **Collegamenti preferiti**, che contiene percorsi personalizzati. Le <xref:System.Windows.Forms.OpenFileDialog> classi <xref:System.Windows.Forms.SaveFileDialog> e consentono<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> di aggiungere cartelle alla raccolta.  
  
> [!NOTE]
> Affinché una posizione personalizzata venga visualizzata <xref:System.Windows.Forms.OpenFileDialog> in o <xref:System.Windows.Forms.SaveFileDialog>, la <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà deve essere impostata su `true` (impostazione predefinita).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Per aggiungere un percorso personalizzato a una finestra di dialogo File  
  
- Aggiungere un percorso, un GUID della cartella nota o un <xref:System.Windows.Forms.FileDialogCustomPlace> oggetto <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> alla raccolta della finestra di dialogo.  
  
     L'esempio di codice riportato di seguito illustra come aggiungere un percorso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUID di cartella nota per percorsi personalizzati della finestra di dialogo File](known-folder-guids-for-file-dialog-custom-places.md)
