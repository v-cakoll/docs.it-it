---
title: 'Procedura: Implementare una proprietà di dipendenza'
description: Definire una proprietà di dipendenza in Windows Presentation Foundation, eseguendo il backup di una proprietà Common Language Runtime con un campo DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165099"
---
# <a name="how-to-implement-a-dependency-property"></a>Procedura: Implementare una proprietà di dipendenza
In questo esempio viene illustrato come eseguire il backup di una proprietà Common Language Runtime (CLR) con un <xref:System.Windows.DependencyProperty> campo, definendo in tal modo una proprietà di dipendenza. Quando si definiscono proprietà personalizzate e si vuole che supportino molti aspetti della funzionalità [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], inclusi stili, data binding, ereditarietà, animazione e valori predefiniti, è necessario implementarle come proprietà di dipendenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene innanzitutto registrata una proprietà di dipendenza chiamando il <xref:System.Windows.DependencyProperty.Register%2A> metodo. Il nome del campo dell'identificatore utilizzato per archiviare il nome e le caratteristiche della proprietà di dipendenza deve essere l'oggetto <xref:System.Windows.DependencyProperty.Name%2A> scelto per la proprietà di dipendenza come parte della <xref:System.Windows.DependencyProperty.Register%2A> chiamata, accodato dalla stringa letterale `Property` . Ad esempio, se si registra una proprietà di dipendenza con un valore <xref:System.Windows.DependencyProperty.Name%2A> di `Location` , il campo identificatore definito per la proprietà di dipendenza deve essere denominato `LocationProperty` .  
  
 In questo esempio, il nome della proprietà di dipendenza e la relativa funzione di accesso CLR è `State` ; il campo identificatore è `StateProperty` , il tipo della proprietà è <xref:System.Boolean> e il tipo che registra la proprietà di dipendenza è `MyStateControl` .  
  
 Se non si riesce a seguire questo criterio di denominazione, la proprietà potrebbe non essere segnalata correttamente nelle finestre di progettazione e alcuni aspetti dell'applicazione di stili del sistema di proprietà potrebbero non funzionare come previsto.  
  
 È anche possibile specificare metadati predefiniti per una proprietà di dipendenza. In questo esempio viene registrato il valore predefinito della proprietà di dipendenza `State` in modo che sia `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Per ulteriori informazioni su come e perché implementare una proprietà di dipendenza, anziché semplicemente eseguire il backup di una proprietà CLR con un campo privato, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Procedure relative](properties-how-to-topics.md)
