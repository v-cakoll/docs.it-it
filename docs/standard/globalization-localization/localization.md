---
title: Localizzazione
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 68e877088c5c3d17b368561b563b4cb17d004e75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278025"
---
# <a name="localization"></a>Localizzazione

La localizzazione è il processo di conversione delle risorse di un'applicazione nelle versioni localizzate per tutte le impostazioni cultura supportate dall'applicazione. È consigliabile passare alla fase di localizzazione solo dopo aver completato il passaggio di [revisione della localizzabilità](localizability-review.md), per verificare che l'applicazione globalizzata sia pronta per la localizzazione.

Un'applicazione pronta per la localizzazione è suddivisa in due blocchi concettuali: un blocco che contiene tutti gli elementi dell'interfaccia utente e un blocco che contiene il codice eseguibile. Il blocco dell'interfaccia utente contiene solo gli elementi dell'interfaccia utente localizzabili, come stringhe, messaggi di errore, finestre di dialogo, menu, risorse oggetto incorporate e così via, per le impostazioni cultura neutre. Il blocco di codice contiene solo il codice dell'applicazione che deve essere usato da tutte le impostazioni cultura supportate. Common Language Runtime supporta un modello di risorse assembly satellite che separa il codice eseguibile dell'applicazione dalle relative risorse. Per altre informazioni sull'implementazione di questo modello, vedere [Risorse nelle app .NET](../../framework/resources/index.md).

Per ogni versione localizzata dell'applicazione, aggiungere un nuovo assembly satellite che contiene il blocco dell'interfaccia utente localizzata tradotto nella lingua appropriata per le impostazioni cultura di destinazione. Il blocco di codice per tutte le impostazioni cultura deve rimanere invariato. La combinazione di una versione localizzata del blocco dell'interfaccia utente con il blocco di codice produce una versione localizzata dell'applicazione.

Windows Software Development Kit (SDK) fornisce l'editor di risorse di Windows Form (Winres.exe) che consente di localizzare rapidamente le risorse Windows Form per le impostazioni cultura di destinazione. Per informazioni sull'uso di questo strumento, vedere [Winres.exe (editor di risorse di Windows Form)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>Vedere anche

- [Globalizzazione e localizzazione](index.md)
- [Revisione della localizzabilità](localizability-review.md)
- [Globalizzazione](globalization.md)
- [Risorse nelle applicazioni desktop](../../framework/resources/index.md)
