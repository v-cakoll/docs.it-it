---
title: 'Mitigazione: Scorrimento orizzontale e virtualizzazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40eaf185e9c0c60493e9a2e5428c58b7463789fe
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a>Mitigazione: Scorrimento orizzontale e virtualizzazione
Questa modifica si applica a un elemento <xref:System.Windows.Controls.ItemsControl> che esegue la propria virtualizzazione in direzione ortogonale alla direzione di scorrimento principale. L'esempio principale è un controllo <xref:System.Windows.Controls.DataGrid> con la proprietà <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A> impostata su `true`.  Il risultato di determinate operazioni di scorrimento orizzontale è stato modificato per produrre risultati più intuitivi e simili ai risultati delle operazioni verticali confrontabili.  Le operazioni specifiche includono **Scorri fino a qui** e **Bordo destro**, per usare i nomi del menu visualizzato facendo clic con il pulsante destro del mouse su una barra di scorrimento orizzontale.  Entrambe le operazioni calcolano un offset candidato ed eseguono una chiamata a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  Dopo lo scorrimento al nuovo offset, la definizione di "qui" o "bordo destro" potrebbe essere stata modificata poiché il contenuto appena devirtualizzato ha modificato il valore di <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName>.  
  
## <a name="description-of-the-change"></a>Descrizione della modifica  
 Nelle versioni precedenti a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], l'operazione di scorrimento usa semplicemente l'offset candidato, anche se potrebbe non essere "qui" o "bordo destro".  Ciò potrebbe risultare in effetti quali il "rimbalzo" dello scorrimento, come illustrato nell'esempio.  Si supponga che un controllo <xref:System.Windows.Controls.DataGrid> abbia <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> impostato su 1000 e <xref:System.Windows.FrameworkElement.Width%2A> impostato su 200.  Uno scorrimento al "Bordo destro" usa l'offset candidato 1000-200 = 800.  Durante lo scorrimento all'offset, le nuove colonne vengono devirtualizzate. Si supponga che siano molto ampie, in modo che <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> venga portato a 2000.  Lo scorrimento termina con <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A> = 800 e il controllo "rimbalza" vicino al centro della barra di scorrimento, esattamente in corrispondenza di 800/2000 = 40%.  
  
 A partire da [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], quando si verifica questa situazione viene ricalcolato un nuovo offset candidato. (Lo scorrimento verticale funziona già in questo modo.)  
  
## <a name="impact"></a>Impatto  
 La modifica produce un'esperienza più prevedibile e intuitiva per l'utente finale, ma può influire anche su qualsiasi applicazione che dipende dal valore esatto di <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> dopo una operazione di scorrimento orizzontale, attivata dall'utente finale o da una chiamata esplicita a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Mitigazione  
 Un'app che usa un valore stimato per <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> dovrebbe essere modificata per recuperare il valore effettivo (e il valore di <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>) dopo qualsiasi scorrimento orizzontale in grado di modificare <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> a causa della devirtualizzazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche al runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)

