---
title: Interoperabilità nativa - .NET
description: Informazioni su come interagire con i componenti nativi in .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 29aacc9210b4103f379b7776c36fc3c29b9e6dec
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857619"
---
# <a name="native-interoperability"></a>Interoperabilità nativa

Gli articoli seguenti illustrano i diversi metodi per implementare l'"interoperabilità nativa" in .NET.

Vari motivi possono rendere necessaria la chiamata del codice nativo:

* Sistemi operativi con un volume elevato di API che non sono presenti nelle librerie di classi gestite. Un ottimo esempio di questo scenario è l'accesso alle funzioni di gestione dell'hardware o del sistema operativo.
* Comunicazione con altri componenti che hanno o possono generare ABI di tipo C (ABI native), ad esempio il codice Java esposto tramite [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o qualsiasi altro linguaggio gestito in grado di creare un componente nativo.
* In Windows la maggior parte del software installato, ad esempio la suite Microsoft Office, registra componenti COM che rappresentano i programmi corrispondenti e consente agli sviluppatori di automatizzarli o di usarli. Anche questo richiede interoperabilità nativa.

L'elenco sopra riportato non esaurisce tutti i potenziali scenari e situazioni in cui lo sviluppatore vuole, preferisce o deve definire un'interfaccia con i componenti nativi. La libreria di classi .NET, ad esempio, usa il supporto per l'interoperabilità nativa per implementare un numero notevole di API, ad esempio il supporto e la manipolazione della console, l'accesso al file system e altro. Tuttavia è importante ricordare che in caso di necessità è disponibile una soluzione alternativa.

> [!NOTE]
> La maggior parte degli esempi riportati in questa sezione viene presentata per tutte e tre le piattaforme supportate in .NET Core (Windows, Linux e macOS). Per alcuni esempi brevi e illustrativi, tuttavia, verrà presentata solo la versione che usa nomi file ed estensioni Windows, come "dll" per le librerie. Questo non significa che le funzionalità illustrate non siano disponibili in Linux o macOS. La scelta dipende solo da motivi di praticità.

## <a name="see-also"></a>Vedere anche

- [Platform Invoke (P/Invoke)](pinvoke.md)
- [Marshalling dei tipi](type-marshalling.md)
- [Procedure consigliate di interoperabilità nativa](best-practices.md)
