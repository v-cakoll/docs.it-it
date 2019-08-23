---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932644"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 Questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per inserire testo in una casella di testo a riga singola. Viene fornito un metodo alternativo per controlli con più righe e testo RTF in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cui non è applicabile. A scopo di confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una sequenza di controlli di testo in un'applicazione di destinazione. Ogni controllo testo viene testato per verificare se è <xref:System.Windows.Automation.ValuePattern> possibile ottenere un oggetto utilizzando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metodo. Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, viene <xref:System.Windows.Automation.ValuePattern.SetValue%2A> usato il metodo per inserire una stringa definita dall'utente nel controllo di testo. In caso contrario <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> , viene utilizzato il metodo.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di testo di inserimento TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
