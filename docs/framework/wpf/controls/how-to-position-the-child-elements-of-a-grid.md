---
title: 'Procedura: posizionare gli elementi figlio di una griglia'
description: Informazioni su come usare i metodi get e set definiti in una griglia Windows Presentation Foundation per posizionare gli elementi figlio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167396"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Procedura: posizionare gli elementi figlio di una griglia
Questo esempio illustra come usare i metodi get e set definiti in <xref:System.Windows.Controls.Grid> per posizionare gli elementi figlio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un <xref:System.Windows.Controls.Grid> elemento padre ( `grid1` ) con tre colonne e tre righe. Un <xref:System.Windows.Shapes.Rectangle> elemento figlio ( `rect1` ) viene aggiunto all'oggetto <xref:System.Windows.Controls.Grid> nella posizione della colonna zero, posizione riga zero. <xref:System.Windows.Controls.Button>gli elementi rappresentano metodi che possono essere chiamati per riposizionare l' <xref:System.Windows.Shapes.Rectangle> elemento all'interno di <xref:System.Windows.Controls.Grid> . Quando un utente fa clic su un pulsante, il metodo correlato viene attivato.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Il seguente esempio di code-behind gestisce i metodi generati dagli <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi del pulsante. L'esempio scrive queste chiamate al metodo in <xref:System.Windows.Controls.TextBlock> elementi che usano metodi Get correlati per restituire i nuovi valori di proprietà come stringhe.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Ecco il risultato finale.

 ![una schermata illustra un'interfaccia utente WPF con due colonne, il lato destro ha una griglia 3 x 3 e i pulsanti a sinistra per spostare un rettangolo colorato tra le colonne e le righe della griglia](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
