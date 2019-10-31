---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198467"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>Caching: Microsoft. Extensions. Caching. SqlServer usa il nuovo pacchetto SqlClient

Il pacchetto `Microsoft.Extensions.Caching.SqlServer` utilizzerà il nuovo pacchetto `Microsoft.Data.SqlClient` anziché il pacchetto `System.Data.SqlClient`. Questa modifica può provocare lievi modifiche di comportamento. Per ulteriori informazioni, vedere [Introducing The New Microsoft. Data. SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il pacchetto `Microsoft.Extensions.Caching.SqlServer` ha usato il pacchetto `System.Data.SqlClient`.

#### <a name="new-behavior"></a>Nuovo comportamento

`Microsoft.Extensions.Caching.SqlServer` USA ora il pacchetto `Microsoft.Data.SqlClient`.

#### <a name="reason-for-change"></a>Motivo della modifica

`Microsoft.Data.SqlClient` è un nuovo pacchetto compilato da `System.Data.SqlClient`. È qui che verranno eseguite tutte le nuove funzionalità da ora in poi.

#### <a name="recommended-action"></a>Azione consigliata

I clienti non devono preoccuparsi di questa modifica sostanziale a meno che non utilizzino i tipi restituiti dal pacchetto `Microsoft.Extensions.Caching.SqlServer` e li eseguono il cast ai tipi `System.Data.SqlClient`. Se, ad esempio, un utente esegue il cast di un `DbConnection` al [tipo SqlConnection precedente](xref:System.Data.SqlClient.SqlConnection), sarà necessario modificare il cast al nuovo tipo `Microsoft.Data.SqlClient.SqlConnection`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
