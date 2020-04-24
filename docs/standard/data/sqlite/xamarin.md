---
title: Limitazioni di Novell
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni che si verificheranno quando si usa Novell.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447167"
---
# <a name="xamarin-limitations"></a>Limitazioni di Novell

Microsoft. Data. SQLite è destinato .NET Standard 2,0 ed è supportato in Novell. La tabella seguente illustra le piattaforme per cui il bundle SQLitePCLRaw predefinito fornisce file binari SQLite nativi. Vedere [versioni personalizzate di SQLite](custom-versions.md) per informazioni dettagliate sull'uso di un bundle diverso o per fornire file binari SQLite nativi.

| Piattaforma | File binari SQLite |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Novell. Mac** | ✔ |
| **Novell. TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft. Data. sqlite tenta di inizializzare automaticamente i bundle SQLitePCLRaw. Sfortunatamente, a causa delle limitazioni della compilazione AOT (Ahead of Time) per Novell. iOS, il tentativo ha esito negativo e viene ricevuto l'errore seguente.

> È necessario chiamare `SQLitePCL.raw.SetProvider()`. Se si usa un pacchetto di bundle, questa operazione viene eseguita chiamando `SQLitePCL.Batteries.Init()`.

Per inizializzare il bundle, aggiungere la seguente riga di codice all'app prima di usare Microsoft. Data. sqlite.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>Vedi anche

* [Limitazioni asincrone](async.md)
* [Versioni di SQLite personalizzate](custom-versions.md)
