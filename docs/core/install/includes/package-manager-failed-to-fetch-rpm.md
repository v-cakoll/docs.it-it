---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920721"
---

Quando si installa il pacchetto .NET Core, è possibile che venga visualizzato un errore simile a `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`. In generale, questo errore indica che il feed del pacchetto per .NET Core viene aggiornato con le versioni più recenti del pacchetto e che è necessario riprovare più tardi. Durante un aggiornamento, il feed del pacchetto non deve essere disponibile per più di 2 ore. Se questo errore viene visualizzato continuamente per più di due ore, inviare un problema all'<https://github.com/dotnet/core/issues>.
