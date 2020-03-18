---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198467"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>Memorizzazione nella cache: Microsoft.Extensions.Caching.SqlServer utilizza il nuovo pacchetto SqlClient

Il `Microsoft.Extensions.Caching.SqlServer` pacchetto utilizzerà `Microsoft.Data.SqlClient` il `System.Data.SqlClient` nuovo pacchetto anziché il pacchetto. Questa modifica potrebbe causare lievi modifiche di interruzione comportamentale. Per ulteriori informazioni, vedere [Introduzione al nuovo Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il `Microsoft.Extensions.Caching.SqlServer` pacchetto `System.Data.SqlClient` ha usato il pacchetto.

#### <a name="new-behavior"></a>Nuovo comportamento

`Microsoft.Extensions.Caching.SqlServer`sta utilizzando `Microsoft.Data.SqlClient` il pacchetto.

#### <a name="reason-for-change"></a>Motivo della modifica

`Microsoft.Data.SqlClient`è un nuovo pacchetto che `System.Data.SqlClient`è costruito fuori di . È dove tutto il lavoro di nuova funzionalità sarà fatto d'ora in tanto.

#### <a name="recommended-action"></a>Azione consigliata

I clienti non dovrebbero preoccuparsi di questa modifica di rilievo `Microsoft.Extensions.Caching.SqlServer` a meno che `System.Data.SqlClient` non utilizzassero tipi restituiti dal pacchetto e che li esetrae ai tipi. Ad esempio, se un `DbConnection` utente esegue il cast di un al tipo `Microsoft.Data.SqlClient.SqlConnection` [SqlConnection precedente,](xref:System.Data.SqlClient.SqlConnection)avrebbe dovuto modificare il cast nel nuovo tipo.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
