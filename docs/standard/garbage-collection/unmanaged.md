---
title: Pulizia delle risorse non gestite
description: Vedere come pulire le risorse non gestite non gestite da .NET Garbage Collector, ad esempio file, Windows, & connessioni di rete o di database.
ms.date: 05/13/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
ms.openlocfilehash: 07a8d754f1fc2612ae53407fa1b12a1eab7e38f2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599832"
---
# <a name="cleaning-up-unmanaged-resources"></a>Pulizia delle risorse non gestite

Per la maggior parte degli oggetti creati dall'app, è possibile basarsi sulla [Garbage Collector .NET](index.md) per gestire la gestione della memoria. Tuttavia, quando si creano oggetti che includono risorse non gestite, è necessario rilasciare in modo esplicito tali risorse al termine dell'utilizzo. I tipi più comuni di risorse non gestite sono oggetti che eseguono il wrapping delle risorse del sistema operativo, ad esempio file, finestre, connessioni di rete o connessioni di database. Benché il Garbage Collector sia in grado di tenere traccia della durata di un oggetto in cui è incapsulata una risorsa non gestita, non dispone di dati sufficienti per effettuare il rilascio e la pulizia della risorsa non gestita.

Se i tipi utilizzano risorse non gestite, è necessario effettuare le operazioni seguenti:

- Implementare lo [schema Dispose](implementing-dispose.md). Per questa operazione è necessario fornire un' <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementazione per abilitare il rilascio deterministico delle risorse non gestite. Un consumer del tipo chiama <xref:System.IDisposable.Dispose%2A> quando l'oggetto e le risorse che usa non sono più necessari. Il metodo <xref:System.IDisposable.Dispose%2A> rilascia immediatamente le risorse non gestite.

- Nel caso in cui un consumer del tipo dimentichi di chiamare <xref:System.IDisposable.Dispose%2A> , fornire un modo per rilasciare le risorse non gestite. A questo scopo è possibile procedere in due modi:

  - Utilizzare un handle sicuro per eseguire il wrapping della risorsa non gestita. Questa è la tecnica consigliata. Gli handle sicuri derivano dalla <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> classe astratta e includono un <xref:System.Object.Finalize%2A> metodo affidabile. L'utilizzo di un handle sicuro richiede semplicemente l'implementazione dell'interfaccia <xref:System.IDisposable> e la chiamata del metodo <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> dell'handle sicuro nell'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Il finalizzatore dell'handle sicuro viene chiamato automaticamente dal Garbage Collector se non viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>.

    **o**-

  - Eseguire l'override del metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType> . La finalizzazione abilita il rilascio non deterministico delle risorse non gestite quando il consumer di un tipo non riesce a chiamare <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> per l'eliminazione deterministica. Definire un [finalizzatore](../../csharp/programming-guide/classes-and-structs/destructors.md) eseguendo l'override del <xref:System.Object.Finalize%2A?displayProperty=nameWithType> metodo.

  > [!WARNING]
  > Tuttavia, poiché la finalizzazione dell'oggetto può essere un'operazione complessa e soggetta a errori, è consigliabile utilizzare un handle sicuro anziché fornire il proprio finalizzatore.

I consumer del tipo in uso possono quindi chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> direttamente per liberare la memoria utilizzata dalle risorse non gestite. Quando si implementa correttamente un metodo <xref:System.IDisposable.Dispose%2A>, il metodo <xref:System.Object.Finalize%2A> o il proprio override del metodo <xref:System.Object.Finalize%2A?displayProperty=nameWithType> diventa una misura di protezione per la pulizia delle risorse nel caso in cui il metodo <xref:System.IDisposable.Dispose%2A> non venga chiamato.

## <a name="in-this-section"></a>Contenuto della sezione

L' [implementazione di un metodo Dispose](implementing-dispose.md) descrive come implementare il modello Dispose per il rilascio delle risorse non gestite.

[Uso di oggetti che `IDisposable` implementano](using-objects.md) viene descritto il modo in cui i consumer di un tipo garantiscono che <xref:System.IDisposable.Dispose%2A> venga chiamata l'implementazione. `using`A tale scopo, è consigliabile usare l'istruzione C# (o l'Visual Basic `Using` ).

## <a name="reference"></a>Informazioni di riferimento

| Tipo/membro | Descrizione |
|--|--|
| <xref:System.IDisposable?displayProperty=nameWithType> | Viene definito il metodo <xref:System.IDisposable.Dispose%2A> per il rilascio delle risorse non gestite. |
| <xref:System.Object.Finalize%2A?displayProperty=nameWithType> | Provvede alla finalizzazione dell'oggetto se le risorse non gestite non vengono rilasciate dal metodo <xref:System.IDisposable.Dispose%2A>. |
| <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> | Elimina la finalizzazione. Questo metodo viene abitualmente chiamato da un metodo `Dispose` per impedire l'esecuzione di un finalizzatore. |
