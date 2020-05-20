---
ms.openlocfilehash: 49041ce906ab0bb8b9482b79c44302465c4ca788
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702268"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>API di globalizzazione usare le librerie ICU in Windows

.NET 5,0 e versioni successive usano le librerie [International Components for Unicode (ICU)](http://site.icu-project.org/home) per la globalizzazione durante l'esecuzione in Windows 10 May 2019 Update o versioni successive.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, le librerie .NET usavano le API [NLS (National Language Support)](/windows/win32/intl/national-language-support) per la funzionalità di globalizzazione. Ad esempio, le funzioni NLS sono state usate per ottenere i dati delle impostazioni cultura, ad esempio i modelli di formato di data e ora, confrontare le stringhe ed eseguire le maiuscole e minuscole nelle impostazioni cultura appropriate.

A partire da .NET 5,0, se un'app è in esecuzione in Windows 10 May 2019 Update o versioni successive, le librerie .NET usano le API di globalizzazione di [ICU](http://site.icu-project.org/home) . Windows 10 May 2019 Update e versioni successive vengono forniti con la libreria nativa di ICU. Se il Runtime .NET non è in grado di caricare ICU, USA invece NLS.

Questa modifica è stata introdotta per due motivi:

- Le app hanno lo stesso comportamento di globalizzazione su più piattaforme, tra cui Linux, macOS e Windows.
- Le app possono controllare il comportamento di globalizzazione usando librerie ICU personalizzate.

#### <a name="version-introduced"></a>Versione introdotta

.NET 5,0 Preview 4

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione da parte dello sviluppatore. Tuttavia, se si desidera continuare a utilizzare le API di globalizzazione NLS, è possibile impostare un' [opzione di run-time](../../../../docs/core/run-time-config/globalization.md#nls) per ripristinare il comportamento.

#### <a name="category"></a>Category

Globalizzazione

#### <a name="affected-apis"></a>API interessate

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Molti tipi nello <xref:System.Globalization?displayProperty=fullName> spazio dei nomi

<!--

#### Affected APIs

- `T:System.Span%601`
- `T:System.String`
- `N:System.Globalization`

-->
