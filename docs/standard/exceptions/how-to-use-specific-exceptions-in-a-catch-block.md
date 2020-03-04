---
title: 'Procedura: utilizzare eccezioni specifiche in un blocco catch'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: 48b450e579263876725f96e0adfc4c16aac1d869
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160157"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Come usare eccezioni specifiche in un blocco catch

In generale, è buona norma intercettare un tipo di eccezione specifico invece che usare un'istruzione `catch` di base.

Quando si verifica un'eccezione, l'eccezione viene passata nello stack e a ogni blocco catch viene data la possibilità di gestirla. L'ordine delle istruzioni catch è importante. Inserire i blocchi catch per il rilevamento di eccezioni specifiche prima di un blocco catch generale per il rilevamento delle eccezioni per evitare che il compilatore generi un errore. Il blocco catch appropriato viene determinato tramite la corrispondenza del tipo di eccezione al nome dell'eccezione specificato nel blocco catch. Se non è presente alcun blocco catch specifico, l'eccezione viene rilevata da un blocco catch generale, se disponibile.

L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare <xref:System.InvalidCastException>. L'esempio crea una classe denominata `Employee` con un'unica proprietà, il livello del dipendente (`Emlevel`). Il metodo `PromoteEmployee` accetta un oggetto e incrementa il livello del dipendente. Un'eccezione <xref:System.InvalidCastException> si verifica quando viene passata un'istanza di <xref:System.DateTime> al metodo `PromoteEmployee`.

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)
