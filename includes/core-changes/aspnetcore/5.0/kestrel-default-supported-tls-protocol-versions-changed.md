---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803264"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Gheppio: versioni del protocollo TLS supportate predefinite modificate

Il gheppio USA ora le versioni del protocollo TLS predefinite del sistema anziché limitare le connessioni ai protocolli TLS 1,1 e TLS 1,2 come in precedenza.

Questa modifica consente:

* TLS 1,3 da usare per impostazione predefinita negli ambienti che lo supportano.
* TLS 1,0 da usare in alcuni ambienti (ad esempio Windows Server 2016 per impostazione predefinita), che in genere [non è consigliabile](/security/engineering/solving-tls1-problem).

Per informazioni, vedere Issue [DotNet/aspnetcore # 22563](https://github.com/dotnet/aspnetcore/issues/22563).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Preview 6

#### <a name="old-behavior"></a>Comportamento precedente

Il gheppio richiede che le connessioni usino TLS 1,1 o TLS 1,2 per impostazione predefinita.

#### <a name="new-behavior"></a>Nuovo comportamento

Gheppio consente al sistema operativo di scegliere il protocollo migliore da usare e di bloccare i protocolli non sicuri. <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>a questo punto, il valore predefinito è `SslProtocols.None` anziché `SslProtocols.Tls12 | SslProtocols.Tls11` .

#### <a name="reason-for-change"></a>Motivo della modifica

Per impostazione predefinita, la modifica è stata apportata per supportare TLS 1,3 e le versioni future di TLS quando diventano disponibili.

#### <a name="recommended-action"></a>Azione consigliata

A meno che l'app non abbia un motivo specifico per non farlo, è necessario usare i nuovi valori predefiniti. Verificare che il sistema sia configurato in modo da consentire solo i protocolli protetti.

Per disabilitare i protocolli precedenti, eseguire una delle operazioni seguenti:

* Disabilitare i protocolli precedenti, ad esempio TLS 1,0, a livello di sistema con le [istruzioni di Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry). Attualmente è abilitato per impostazione predefinita in tutte le versioni di Windows.
* Selezionare manualmente i protocolli che si desidera supportare nel codice nel modo seguente:

    ```csharp
    using System.Security.Authentication;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

Sfortunatamente, non esiste alcuna API per escludere protocolli specifici.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
