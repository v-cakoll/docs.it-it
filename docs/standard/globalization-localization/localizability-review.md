---
title: Revisione della localizzabilità
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1907841694cde82cebada4a9e73b8ce703208611
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576129"
---
# <a name="localizability-review"></a>Revisione della localizzabilità
La revisione della localizzabilità è un passaggio intermedio nello sviluppo di un'applicazione internazionale. Viene verificato che un'applicazione globalizzata sia pronta per la localizzazione e viene identificato qualsiasi codice o aspetto dell'interfaccia utente per cui è richiesta una gestione speciale. Questo passaggio consente di garantire che durante il processo di localizzazione non verranno introdotti difetti funzionali nell'applicazione. Quando tutti i problemi generati dall'analisi della localizzazione vengono risolti, l'applicazione è pronta per la localizzazione. Se la revisione della localizzabilità è completa, non è necessario modificare nessun codice sorgente durante il processo di localizzazione.  
  
 La revisione della localizzabilità è costituita dai tre controlli seguenti:  
  
-   [I requisiti di globalizzazione sono implementati?](#global)  
  
-   [Le funzionalità dipendenti dalle impostazioni cultura sono gestite correttamente?](#culture)  
  
-   [L'applicazione è stata testata con dati internazionali?](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a>Implementazione dei requisiti di globalizzazione  
 Se l'applicazione è stata progettata e sviluppata pensando alla localizzazione e se sono stati seguiti i consigli forniti nell'articolo [Globalizzazione](../../../docs/standard/globalization-localization/globalization.md), la revisione della localizzabilità sarà principalmente un passaggio di controllo di qualità. In caso contrario, durante questa fase sarà necessario rivedere e implementare i consigli per la [globalizzazione](../../../docs/standard/globalization-localization/globalization.md) e correggere gli errori nel codice sorgente che impediscono la localizzazione.  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a>Gestione delle funzionalità dipendenti dalle impostazioni cultura  
 .NET Framework non fornisce supporto a livello di codice in numerose aree che variano notevolmente in base alle impostazioni cultura. Nella maggior parte dei casi, è necessario scrivere codice personalizzato per gestire le aree funzionali come segue:  
  
-   Indirizzi.  
  
-   Numeri di telefono.  
  
-   Formati di carta.  
  
-   Unità di misura utilizzate per le lunghezze, i pesi, l'area, il volume e le temperature. Benché .NET Framework non offra il supporto predefinito per la conversione tra le unità di misura, è possibile utilizzare la proprietà <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> per determinare se in un paese o un'area particolare viene utilizzato il sistema metrico, come illustrato di seguito.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a>Test dell'applicazione  
 Prima di localizzare l'applicazione, è necessario testarla utilizzando i dati internazionali in versioni internazionali del sistema operativo. Sebbene la maggior parte dell'interfaccia utente non sarà localizzata in questa fase, sarà possibile rilevare problemi come i seguenti:  
  
-   I dati serializzati che non si deserializzano correttamente nelle versioni del sistema operativo.  
  
-   Dati numerici che non riflettono le convenzioni delle impostazioni cultura correnti. Ad esempio, i numeri possono essere visualizzati con separatori di gruppi, separatori decimali o simboli di valuta non corretti.  
  
-   Informazioni di data e ora che non riflettono le convenzioni delle impostazioni cultura correnti. Ad esempio, i numeri che rappresentano il mese e il giorno possono essere visualizzati nell'ordine errato e i separatori di data o le informazioni sul fuso orario possono essere errati.  
  
-   Risorse che non sono disponibili in quanto non sono identificate le impostazioni cultura predefinite per l'applicazione.  
  
-   Stringhe visualizzate in modo anomalo per le impostazioni cultura specifiche.  
  
-   Confronti di stringhe o confronti per l'uguaglianza tramite cui vengono restituiti risultati imprevisti.  
  
 Se durante lo sviluppo dell'applicazione sono stati seguiti i consigli per la globalizzazione, le funzionalità dipendenti dalle impostazioni cultura sono state gestite correttamente e i problemi di localizzazione riscontrati durante i test sono stati identificati e risolti, è possibile procedere al passaggio successivo, [Localizzazione](../../../docs/standard/globalization-localization/localization.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)  
 [Localizzazione](../../../docs/standard/globalization-localization/localization.md)  
 [Globalizzazione](../../../docs/standard/globalization-localization/globalization.md)  
 [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)
