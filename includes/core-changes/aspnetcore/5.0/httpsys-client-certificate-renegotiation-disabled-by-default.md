---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325237"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: rinegoziazione certificato client disabilitata per impostazione predefinita

L'opzione per rinegoziare una connessione e richiedere un certificato client è stata disabilitata per impostazione predefinita. Per informazioni, vedere Issue [DotNet/aspnetcore # 23181](https://github.com/dotnet/aspnetcore/issues/23181).

#### <a name="version-introduced"></a>Versione introdotta

ASP.NET Core 5,0

#### <a name="old-behavior"></a>Comportamento precedente

È possibile rinegoziare la connessione per richiedere un certificato client.

#### <a name="new-behavior"></a>Nuovo comportamento

I certificati client possono essere richiesti solo durante l'handshake di connessione iniziale. Per altre informazioni, vedere richiesta pull [DotNet/aspnetcore # 23162](https://github.com/dotnet/aspnetcore/pull/23162).

#### <a name="reason-for-change"></a>Motivo della modifica

La rinegoziazione ha causato un certo numero di problemi di prestazioni e deadlock. Non è inoltre supportata in HTTP/2. Per un contesto aggiuntivo da quando l'opzione per controllare questo comportamento è stata introdotta in ASP.NET Core 3,1, vedere Issue [DotNet/aspnetcore # 14806](https://github.com/dotnet/aspnetcore/issues/14806).

#### <a name="recommended-action"></a>Azione consigliata

Le app che richiedono certificati client devono usare *netsh.exe* per impostare l' `clientcertnegotiation` opzione su `enabled` . Per ulteriori informazioni, vedere [comandi netsh http](/windows-server/networking/technologies/netsh/netsh-http).

Se si vuole che i certificati client siano abilitati solo per alcune parti dell'app, vedere le linee guida per i [certificati client facoltativi](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).

Se è necessario il comportamento precedente della rinegoziazione, impostare sul `HttpSysOptions.ClientCertificateMethod` valore precedente `ClientCertificateMethod.AllowRenegotiate` . Questa operazione non è consigliata per i motivi illustrati sopra e nelle linee guida collegate.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
