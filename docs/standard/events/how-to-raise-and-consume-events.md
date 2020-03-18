---
title: 'Procedura: generare e utilizzare eventi'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 256b5ae9ac2145e339136985872dfa5423aca730
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73131589"
---
# <a name="how-to-raise-and-consume-events"></a>Procedura: generare e utilizzare eventi
Gli esempi in questo argomento illustrano come usare gli eventi. Sono inclusi esempi del delegato <xref:System.EventHandler>, del delegato <xref:System.EventHandler%601> e di un delegato personalizzato, per illustrare gli eventi con e senza dati.  
  
 Gli esempi usano i concetti descritti nell'articolo [Eventi](../../../docs/standard/events/index.md).  
  
## <a name="example"></a>Esempio  
 Il primo esempio mostra come generare e utilizzare un evento che non ha dati. Contiene una classe denominata `Counter` che ha un evento denominato `ThresholdReached`. Questo evento viene generato quando un valore di un contatore è maggiore o uguale a un valore soglia. Il delegato <xref:System.EventHandler> è associato all'evento, perché non vengono forniti dati dell'evento.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come generare e utilizzare un evento che fornisce i dati. Il delegato <xref:System.EventHandler%601> è associato all'evento e viene fornita un'istanza di un oggetto dati evento personalizzato.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come dichiarare un delegato per un evento. Il delegato è denominato `ThresholdReachedEventHandler`. Si tratta solo di un esempio. In genere, non è necessario dichiarare un delegato per un evento, perché è possibile usare il delegato <xref:System.EventHandler> o <xref:System.EventHandler%601>. È necessario dichiarare un delegato solo in rari casi, ad esempio per rendere la classe disponibile per il codice legacy che non può usare generics.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Events](../../../docs/standard/events/index.md)
