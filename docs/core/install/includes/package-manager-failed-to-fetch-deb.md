---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920640"
---

Quando si installa il pacchetto .NET Core, è possibile che venga visualizzato un errore simile a `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`. In generale, questo errore indica che il feed del pacchetto per .NET Core viene aggiornato con le versioni più recenti del pacchetto e che è necessario riprovare più tardi. Durante un aggiornamento, il feed del pacchetto non deve essere disponibile per più di 30 minuti. Se questo errore viene visualizzato continuamente per più di 30 minuti, inviare un problema all'<https://github.com/dotnet/core/issues>.
