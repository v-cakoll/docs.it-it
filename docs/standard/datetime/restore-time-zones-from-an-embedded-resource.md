---
title: 'Procedura: ripristinare fusi orari da una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31dd785c419d9a8e11eb23deabd2dfa71c4d6e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572346"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Procedura: ripristinare fusi orari da una risorsa incorporata

In questo argomento viene descritto come ripristinare i fusi orari che sono stati salvati in un file di risorse. Per informazioni e istruzioni sul salvataggio di fusi orari, vedere [procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata

1. Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza utilizzando il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo.

2. Creare un'istanza di un <xref:System.Resources.ResourceManager> oggetto passando il nome completo del file di risorse incorporate e un riferimento all'assembly che contiene il file di risorse.

   Se è possibile determinare il nome completo del file di risorse incorporato, utilizzare il [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly. Un `.mresource` voce identifica la risorsa. Nell'esempio, è il nome della risorsa completo `SerializeTimeZoneData.SerializedTimeZones`.

   Se il file di risorse è incorporato nello stesso assembly che contiene il codice di creazione di un'istanza del fuso orario, è possibile recuperare un riferimento a esso tramite la chiamata di `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> metodo.

3. Se la chiamata al <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo ha esito negativo, o se deve essere creata un'istanza di un fuso orario personalizzato, recuperare una stringa che contiene il fuso orario serializzato chiamando il <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> metodo.

4. Deserializzare i dati del fuso orario chiamando il <xref:System.TimeZoneInfo.FromSerializedString%2A> metodo.

## <a name="example"></a>Esempio

Nell'esempio seguente viene deserializzato un <xref:System.TimeZoneInfo> oggetto archiviato in un file di risorse .NET XML incorporato.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Questo codice viene illustrata la gestione delle eccezioni per garantire che un <xref:System.TimeZoneInfo> è presente l'oggetto richiesto dall'applicazione. Tenta innanzitutto di creare un'istanza di un <xref:System.TimeZoneInfo> oggetto recuperandolo dal Registro di sistema utilizzando il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo. Se il fuso orario non può essere creata un'istanza, il codice recupera dal file di risorse incorporate.

Perché dati per i fusi orari personalizzati (fusi orari creata un'istanza utilizzando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo) non sono archiviate nel Registro di sistema, non chiamare il codice il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza il fuso orario per Palmer, Antartide. Al contrario, Cerca immediatamente il file di risorse incorporate per recuperare una stringa che contiene i dati del fuso orario prima di chiamare il <xref:System.TimeZoneInfo.FromSerializedString%2A> metodo.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Un riferimento a System.Core.dll e di Forms essere aggiunto al progetto.

* Che importati spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md)
[procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
