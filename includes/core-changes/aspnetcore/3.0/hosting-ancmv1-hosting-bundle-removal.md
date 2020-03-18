---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901737"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle

A partire da ASP.NET Core 3.0, il pacchetto di hosting di Windows non conterrà AspNetCoreModule (ANCM) V1.

ANCM V2 è compatibile con le versioni precedenti di ANCM OutOfProcess ed è consigliato per l'uso con le app ASP.NET Core 3.0.

Per una discussione, vedere [dotnet/aspnetcore-7095](https://github.com/dotnet/aspnetcore/issues/7095).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

ANCM V1 è incluso nel pacchetto di hosting di Windows.

#### <a name="new-behavior"></a>Nuovo comportamento

ANCM V1 non è incluso nel pacchetto di hosting di Windows.

#### <a name="reason-for-change"></a>Motivo della modifica

ANCM V2 è compatibile con le versioni precedenti di ANCM OutOfProcess ed è consigliato per l'uso con le app ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Azione consigliata

Usa ANCM V2 con ASP.NET app Core 3.0.

Se è richiesto ANCM V1, può essere installato utilizzando il ASP.NET Core 2.1 o 2.2 Windows Hosting Bundle.

Questa modifica interromperà ASP.NET le app Core 3.0 che:This change will break ASP.NET Core 3.0 apps that:

- Esplicitamente optato per `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`l'utilizzo di ANCM V1 con .
- Disporre di un file `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />` *web.config* personalizzato con .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
