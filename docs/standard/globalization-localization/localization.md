---
title: Localizzazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a>Localizzazione
Localizzazione è il processo di conversione di risorse dell'applicazione nelle versioni localizzate per tutte le impostazioni cultura supportate dall'applicazione. È consigliabile procedere alla fase di localizzazione solo dopo aver completato il [revisione della localizzabilità](../../../docs/standard/globalization-localization/localizability-review.md) passaggio per verificare che l'applicazione globalizzata sia pronta per la localizzazione.  
  
 Un'applicazione che è pronta per la localizzazione viene suddivisa in due blocchi concettuali, un blocco che contiene tutti gli elementi di interfaccia utente e un blocco che contiene il codice eseguibile. Il blocco dell'interfaccia utente contiene solo gli elementi dell'interfaccia utente localizzabili, ad esempio stringhe, messaggi di errore, finestre di dialogo, menu, le risorse di oggetti incorporati e così via per la lingua. Il blocco di codice contiene solo il codice dell'applicazione utilizzabile da tutte le lingue supportate. Common language runtime supporta un modello di risorsa di assembly satellite che separa il codice dell'applicazione eseguibile dalle relative risorse. Per ulteriori informazioni sull'implementazione di questo modello, vedere [risorse nelle applicazioni Desktop](../../../docs/framework/resources/index.md).  
  
 Per ogni versione localizzata dell'applicazione, aggiungere un nuovo assembly satellite che contiene il blocco dell'interfaccia utente localizzata tradotto nella lingua appropriata per le impostazioni cultura di destinazione. Il blocco di codice per tutte le impostazioni cultura deve rimanere invariate. La combinazione di una versione localizzata del blocco dell'interfaccia utente con il blocco di codice produce una versione localizzata dell'applicazione.  
  
 Il [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] fornisce l'Editor di risorse form (Winres.exe) di Windows che consente di localizzare rapidamente Windows Form per le lingue di destinazione. Per informazioni sull'utilizzo di questo strumento, vedere [Winres.exe (Editor di risorse di Windows Form)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)  
 [Revisione della localizzabilità](../../../docs/standard/globalization-localization/localizability-review.md)  
 [Globalizzazione](../../../docs/standard/globalization-localization/globalization.md)  
 [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)
