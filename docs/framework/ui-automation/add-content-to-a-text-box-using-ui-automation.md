---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
description: Vedere un esempio di come aggiungere contenuto a una casella di testo a riga singola usando l'automazione interfaccia utente di Microsoft in .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 4136d460de7091a515580cade16f06e54699727a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166920"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per inserire testo in una casella di testo a riga singola. Viene fornito un metodo alternativo per controlli con più righe e testo RTF in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile. A scopo di confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una sequenza di controlli di testo in un'applicazione di destinazione. Ogni controllo testo viene testato per verificare se è <xref:System.Windows.Automation.ValuePattern> possibile ottenere un oggetto utilizzando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metodo. Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern> , <xref:System.Windows.Automation.ValuePattern.SetValue%2A> viene usato il metodo per inserire una stringa definita dall'utente nel controllo di testo. In caso contrario, <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene utilizzato il metodo.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di testo di inserimento TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
