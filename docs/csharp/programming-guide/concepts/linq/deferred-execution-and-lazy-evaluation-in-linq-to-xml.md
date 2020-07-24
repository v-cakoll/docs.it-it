---
title: Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)
description: Le operazioni query e Axis possono usare l'esecuzione posticipata in C#. Informazioni sui requisiti e i vantaggi dell'esecuzione posticipata e considerazioni sull'implementazione.
ms.date: 07/20/2015
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
ms.openlocfilehash: 8559505572404f895d75e0d9895f9ae2c07b795e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105456"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a>Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)
Operazioni di query e su asse vengono spesso implementate in modo da usare l'esecuzione posticipata. In questo argomento vengono illustrati requisiti e vantaggi dell'esecuzione posticipata e vengono fornite alcune considerazioni sull'implementazione.  
  
## <a name="deferred-execution"></a>Esecuzione posticipata  
 Per esecuzione posticipata si intende che la valutazione di un'espressione viene ritardata finché il relativo valore *realizzato* non risulta effettivamente necessario. L'esecuzione posticipata può contribuire a migliorare notevolmente le prestazioni quando è necessario modificare grandi raccolte di dati, in particolare in programmi che contengono una serie di modifiche o query concatenate. Nel migliore dei casi l'esecuzione posticipata consente di eseguire un'unica iterazione nella raccolta di origine.  
  
 Le tecnologie LINQ usano notevolmente l'esecuzione posticipata sia nei membri di classi <xref:System.Linq?displayProperty=nameWithType> principali che nei metodi di estensione dei diversi spazi dei nomi LINQ, ad esempio <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.  
  
 L'esecuzione posticipata è supportata direttamente nel linguaggio C# usando la parola chiave [yield](../../../language-reference/keywords/yield.md) (sotto forma di istruzione `yield-return`) quando viene usata all'interno di un blocco iteratore. Tale iteratore deve restituire una raccolta di tipo <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> (o un tipo derivato).  
  
## <a name="eager-vs-lazy-evaluation"></a>Valutazione eager e valutazione lazy  
 Quando si scrive un metodo che implementa l'esecuzione posticipata, è inoltre necessario decidere se implementare il metodo tramite la valutazione lazy o la valutazione eager.  
  
- Nella *valutazione lazy* durante ogni chiamata all'iteratore viene elaborato un unico elemento della raccolta di origine. Si tratta della modalità di implementazione tipica degli iteratori.  
  
- Nella *valutazione eager* in seguito alla prima chiamata all'iteratore verrà elaborata l'intera raccolta. Potrebbe inoltre essere necessaria una copia temporanea della raccolta di origine. Ad esempio, il metodo <xref:System.Linq.Enumerable.OrderBy%2A> deve ordinare l'intera raccolta prima di restituire il primo elemento.  
  
 La valutazione lazy offre in genere prestazioni migliori perché implica una distribuzione uniforme dell'overhead di elaborazione in tutte le fasi della valutazione della raccolta e riduce al minimo l'uso di dati temporanei. Per alcune operazioni è naturalmente inevitabile dover materializzare i risultati intermedi.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Nel successivo argomento dell'esercitazione verrà illustrata l'esecuzione posticipata:  
  
- [Esempio di esecuzione posticipata (C#)](./deferred-execution-example.md)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: Concatenamento di query (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
- [Concetti e terminologia (trasformazione funzionale) (C#)](./concepts-and-terminology-functional-transformation.md)
- [Operazioni di aggregazione (C#)](./aggregation-operations.md)
- [yield](../../../language-reference/keywords/yield.md)
