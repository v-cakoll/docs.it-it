---
title: Limitazioni di elegante
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni che si verificheranno quando si usa l'elegante.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901204"
---
# <a name="dapper-limitations"></a>Limitazioni di elegante

Quando si usa Microsoft. Data. sqlite con [elegante](https://stackexchange.github.io/Dapper/), è necessario tenere presenti alcune limitazioni.

## <a name="parameters"></a>Parametri

I nomi dei parametri SQLite fanno distinzione tra maiuscole e minuscole. Verificare che i nomi di parametro usati in SQL corrispondano al caso delle proprietà dell'oggetto anonimo. Il problema [#18861](https://github.com/dotnet/efcore/issues/18861) potrebbe migliorare questa esperienza.

L'utilizzo del prefisso `@` è previsto anche per i parametri. Gli altri prefissi non funzioneranno.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Tipi di dati

Elegante legge i valori usando l'indicizzatore SqliteDataReader. Il tipo restituito di questo indicizzatore è Object, il che significa che restituirà solo valori Long, Double, String o byte []. Per ulteriori informazioni, vedere [tipi di dati](types.md). L'elegante gestisce la maggior parte delle conversioni tra questi e altri tipi primitivi. Sfortunatamente, non gestisce `DateTimeOffset`, `Guid`o `TimeSpan`. Creare gestori di tipi se si vuole usare questi tipi nei risultati.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

Non dimenticare di aggiungere i gestori di tipi prima di eseguire una query.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>Vedere anche

* [Tipi di dati](types.md)
* [Limitazioni asincrone](async.md)
