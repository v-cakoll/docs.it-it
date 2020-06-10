---
title: "Procedura: creare eccezioni definite dall'utente"
description: Informazioni su come creare eccezioni definite dall'utente, che rappresentano un'alternativa alla gerarchia di classi di eccezioni derivate dalla classe di base Exception in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
ms.openlocfilehash: 14eb6246ba4347f33766f7dff36463f2bf996330
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662797"
---
# <a name="how-to-create-user-defined-exceptions"></a>Come creare eccezioni definite dall'utente

.NET offre una gerarchia di classi di eccezioni derivate dalla classe di base <xref:System.Exception>. Tuttavia, se nessuna delle eccezioni predefinite soddisfa le proprie esigenze, è possibile creare classi di eccezioni personalizzate mediante la derivazione dalla classe <xref:System.Exception>.

Quando si creano eccezioni personalizzate, terminare il nome della classe dell'eccezione definita dall'utente con la parola "Exception" e implementare i tre costruttori comuni, come illustrato nell'esempio seguente. L'esempio definisce una nuova classe di eccezione denominata `EmployeeListNotFoundException`. La classe è derivata da <xref:System.Exception> e include tre costruttori.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> Nei casi in cui viene usata la comunicazione remota, è necessario assicurarsi che i metadati di tutte le eccezioni definite dall'utente siano disponibili nel server chiamato e nel client (oggetto proxy o chiamante). Per ulteriori informazioni, vedere [procedure consigliate per le eccezioni](best-practices-for-exceptions.md).

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)
