---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394093"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Hosting: AspNetCoreModule V1 rimosso dal bundle di hosting di Windows

A partire da ASP.NET Core 3,0, il bundle di hosting di Windows non conterrà AspNetCoreModule (modulo ASP.NET Core) V1.

MODULO ASP.net core V2 è compatibile con le versioni precedenti di modulo ASP.NET Core OutOfProcess ed è consigliato per l'uso con app ASP.NET Core 3,0.

Per informazioni, vedere [ASPNET/AspNetCore # 7095](https://github.com/aspnet/AspNetCore/issues/7095).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

MODULO ASP.NET Core V1 è incluso nel bundle di hosting di Windows.

#### <a name="new-behavior"></a>Nuovo comportamento

MODULO ASP.NET Core V1 non è incluso nel bundle di hosting di Windows.

#### <a name="reason-for-change"></a>Motivo della modifica

MODULO ASP.net core V2 è compatibile con le versioni precedenti di modulo ASP.NET Core OutOfProcess ed è consigliato per l'uso con app ASP.NET Core 3,0.

#### <a name="recommended-action"></a>Azione consigliata

Usare modulo ASP.net core V2 con app ASP.NET Core 3,0.

Se è necessario modulo ASP.NET Core V1, può essere installato usando il bundle di hosting di Windows ASP.NET Core 2,1 o 2,2.

Questa modifica interrompe ASP.NET Core app 3,0 che:

- È stato esplicitamente accettato l'uso di modulo ASP.NET Core V1 con `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.
- Disporre di un file *Web. config* personalizzato con `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
