---
title: 'Procedura: generare e utilizzare eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d052c865a554977ce5c8b0a347337d9d9b92fc57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-raise-and-consume-events"></a>Procedura: generare e utilizzare eventi
Gli esempi in questo argomento viene illustrato come utilizzare gli eventi. Gli esempi includono la <xref:System.EventHandler> delegato, il <xref:System.EventHandler%601> delegato e un delegato personalizzato, per illustrare gli eventi con e senza dati.  
  
 Gli esempi utilizzano i concetti illustrati nella sezione di [eventi](../../../docs/standard/events/index.md) articolo.  
  
## <a name="example"></a>Esempio  
 Nel primo esempio viene illustrato come generare e utilizzare un evento che non dispone di dati. Contiene una classe denominata `Counter` che dispone di un evento denominato `ThresholdReached`. Questo evento viene generato quando un valore uguale o maggiore di un valore soglia. Il <xref:System.EventHandler> delegato è associato all'evento, perché non è stato specificato nessun dato dell'evento.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come generare e utilizzare un evento che fornisce i dati. Il <xref:System.EventHandler%601> delegato è associato all'evento e viene fornita un'istanza di un oggetto dati di evento personalizzato.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come dichiarare un delegato per un evento. Il delegato denominato `ThresholdReachedEventHandler`. Questa è solo un'illustrazione. In genere, non è necessario dichiarare un delegato per un evento, poiché è possibile utilizzare il <xref:System.EventHandler> o <xref:System.EventHandler%601> delegato. È necessario dichiarare un delegato solo in rari scenari, ad esempio, per la classe disponibile per il codice legacy che non è possibile utilizzare generics.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../docs/standard/events/index.md)
