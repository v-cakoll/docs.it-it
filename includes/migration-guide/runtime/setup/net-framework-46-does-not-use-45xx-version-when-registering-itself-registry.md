---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774204"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>.NET Framework 4.6 non usa una versione 4.5.x.x durante la registrazione nel Registro di sistema

|   |   |
|---|---|
|Dettagli|Come prevedibile, il set di chiavi della versione nel Registro di sistema (in <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) per .NET Framework 4.6 inizia con "4.6" e non "4.5". Le app che dipendono da queste chiavi del Registro di sistema per conoscere le versioni di .NET Framework installate in un computer devono essere aggiornate in modo da comprendere che 4.6 è una nuova versione possibile che è compatibile con le precedenti versioni 4.5.x.|
|Suggerimento|Aggiornare le app che sondano un'installazione di .NET Framework 4.5 cercando le chiavi del Registro di sistema 4.5 in modo che accettino anche la versione 4.6.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Runtime|
