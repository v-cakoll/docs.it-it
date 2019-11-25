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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File
Nelle finestre di dialogo predefinite Apri e Salva in Windows Vista è presente un'area sul lato sinistro della finestra di dialogo denominata **collegamenti preferiti**. che contiene percorsi personalizzati. Le classi <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> consentono di aggiungere cartelle alla raccolta di <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>.  
  
> [!NOTE]
> Affinché una posizione personalizzata venga visualizzata nella <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, la proprietà <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> deve essere impostata su `true` (impostazione predefinita).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Per aggiungere un percorso personalizzato a una finestra di dialogo File  
  
- Aggiungere un percorso, un GUID della cartella nota o un oggetto <xref:System.Windows.Forms.FileDialogCustomPlace> alla raccolta <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> della finestra di dialogo.  
  
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
