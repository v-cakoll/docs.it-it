---
title: 'Procedura: Implementare una proprietà di dipendenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: e2f18cb3941be2ebf4315a844c05b91ff49c6aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757456"
---
# <a name="how-to-implement-a-dependency-property"></a>Procedura: Implementare una proprietà di dipendenza
Questo esempio illustra come eseguire una [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] proprietà con un <xref:System.Windows.DependencyProperty> campo, definendo una proprietà di dipendenza. Quando si definiscono proprietà personalizzate e si vuole che supportino molti aspetti della funzionalità [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], inclusi stili, data binding, ereditarietà, animazione e valori predefiniti, è necessario implementarle come proprietà di dipendenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente registra prima di tutto una proprietà di dipendenza chiamando il <xref:System.Windows.DependencyProperty.Register%2A> (metodo). Il nome del campo dell'identificatore che viene usato per archiviare il nome e le caratteristiche della proprietà di dipendenza deve essere il <xref:System.Windows.DependencyProperty.Name%2A> scelto per la proprietà di dipendenza come parte del <xref:System.Windows.DependencyProperty.Register%2A> chiamata, aggiunta dalla stringa letterale `Property`. Ad esempio, se si registra una proprietà di dipendenza con un <xref:System.Windows.DependencyProperty.Name%2A> dei `Location`, quindi il campo dell'identificatore definito per la proprietà di dipendenza deve essere denominato `LocationProperty`.  
  
 In questo esempio, il nome della proprietà di dipendenza e il relativo [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor `State`; il campo dell'identificatore `StateProperty`; il tipo della proprietà è <xref:System.Boolean>; e il tipo che registra la proprietà di dipendenza è `MyStateControl`.  
  
 Se non si riesce a seguire questo criterio di denominazione, la proprietà potrebbe non essere segnalata correttamente nelle finestre di progettazione e alcuni aspetti dell'applicazione di stili del sistema di proprietà potrebbero non funzionare come previsto.  
  
 È anche possibile specificare metadati predefiniti per una proprietà di dipendenza. In questo esempio viene registrato il valore predefinito della proprietà di dipendenza `State` in modo che sia `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Per altre informazioni su come e perché implementare una proprietà di dipendenza, in contrapposizione al semplice supporto di una proprietà [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con un campo privato, vedere [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Procedure relative alle proprietà](properties-how-to-topics.md)
