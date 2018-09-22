---
title: "Procedura: creare un'istanza di un oggetto TimeZoneInfo"
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c8ff38325e26dd1bc946f6f12c365b6dea3e228
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576678"
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Procedura: creare un'istanza di un oggetto TimeZoneInfo

Il modo più comune per creare un'istanza di un oggetto <xref:System.TimeZoneInfo> è recuperare le relative informazioni dal Registro di sistema. In questo argomento viene illustrato come creare un'istanza di un oggetto <xref:System.TimeZoneInfo> dal Registro di sistema locale.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Per creare un'istanza di un oggetto TimeZoneInfo

1. Dichiarare un oggetto <xref:System.TimeZoneInfo> .

2. Chiamare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> (metodo).

3. Gestire tutte le eccezioni generate dal metodo, in particolare <xref:System.TimeZoneNotFoundException> , generata se il fuso orario non è definito nel Registro di sistema.

## <a name="example"></a>Esempio

Nel codice seguente viene recuperato un oggetto <xref:System.TimeZoneInfo> che rappresenta il fuso Ora solare fuso orientale e viene visualizzata l'Ora solare fuso orientale che corrisponde all'ora locale.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

Il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> unico parametro del metodo è l'identificatore del fuso orario da recuperare, che corrisponde all'oggetto <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> proprietà. L'identificatore del fuso orario è un campo chiave che identifica in modo univoco il fuso orario. Benché la maggior parte delle chiavi sia relativamente breve, in confronto l'identificatore del fuso orario è piuttosto lungo. In molti casi, il valore corrisponde alla proprietà <xref:System.TimeZoneInfo.StandardName%2A> di un oggetto <xref:System.TimeZoneInfo> , usato per fornire il nome dell'ora solare del fuso orario. Esistono tuttavia alcune eccezioni. Il modo migliore per verificare che venga fornito un identificatore valido consiste nell'enumerare i fusi orari disponibili nel sistema e annotare i relativi identificatori dei fusi orari. Per informazioni generali, vedere [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md). Nell'argomento [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) è presente inoltre un elenco di identificatori dei fusi orari selezionati.

Se il fuso orario viene trovato, il metodo restituisce l'oggetto <xref:System.TimeZoneInfo> . Se il fuso orario non viene trovato, il metodo genera un'eccezione <xref:System.TimeZoneNotFoundException>. Se invece il fuso orario viene trovato ma i dati sono danneggiati o incompleti, il metodo genera un'eccezione <xref:System.InvalidTimeZoneException>.

Se l'applicazione si basa su un fuso orario che deve essere presente, chiamare prima il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per recuperare le informazioni del fuso orario dal Registro di sistema. Se la chiamata al metodo non riesce, il gestore di eccezioni deve creare una nuova istanza del fuso orario o deve ricrearlo deserializzando un oggetto <xref:System.TimeZoneInfo> serializzato. Visualizzare [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) per un esempio.

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Procedura: Accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](../../../docs/standard/datetime/access-utc-and-local.md)
