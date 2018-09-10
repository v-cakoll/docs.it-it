---
title: Operazioni sulle stringhe indipendenti dalle impostazioni cultura
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1e1b476a1de1f0c348e264c9dc6b42ceb81eff
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869341"
---
# <a name="culture-insensitive-string-operations"></a>Operazioni sulle stringhe indipendenti dalle impostazioni cultura
Le operazioni eseguite sulle stringhe dipendenti dalle impostazioni cultura possono costituire un vantaggio nella creazione di applicazioni progettate per la visualizzazione dei risultati in base alle impostazioni cultura. Per impostazione predefinita, i metodi dipendenti dalle impostazioni cultura ottengono le impostazioni cultura da utilizzare dalla proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A> del thread corrente.  
  
 Si noti che le operazioni sulle stringhe dipendenti dalle impostazioni cultura, tuttavia, non sempre corrispondono al comportamento desiderato. L'utilizzo di operazioni dipendenti dalle impostazioni cultura nei casi in cui è preferibile che i risultati siano indipendenti dalle impostazioni cultura può determinare errori nel codice dell'applicazione per le impostazioni cultura con mappatura di maiuscole/minuscole personalizzata e regole di ordinamento. Per un esempio, vedere la sezione "Confronti tra stringhe che usano le impostazioni cultura correnti" nell'articolo [Procedure consigliate per l'uso delle stringhe](../../../docs/standard/base-types/best-practices-strings.md).  
  
 L'opportunità di utilizzare operazioni sulle stringhe dipendenti oppure indipendenti dalle impostazioni cultura è determinata dall'utilizzo dei risultati da parte dell'applicazione. È in genere preferibile che le operazioni sulle stringhe che determinano la visualizzazione di risultati siano dipendenti dalle impostazioni cultura. Se in un'applicazione viene visualizzato un elenco ordinato di stringhe localizzate in una casella di riepilogo, ad esempio, l'applicazione dovrebbe eseguire un ordinamento dipendente dalle impostazioni cultura.  
  
 I risultati delle operazioni sulle stringhe utilizzate internamente devono in genere essere indipendenti dalle impostazioni cultura. In generale, se l'applicazione utilizza nomi file, formati di persistenza o informazioni sui simboli che non vengono visualizzati, è opportuno che i risultati delle operazioni sulle stringhe non varino in base alle impostazioni cultura. Se in un'applicazione viene confrontata una stringa per determinare se costituisce un tag XML riconosciuto, ad esempio, il confronto deve essere indipendente dalle impostazioni cultura. Inoltre, se una decisione relativa alla sicurezza è basata sul risultato di un confronto di stringhe o di un'operazione di modifica di maiuscole e minuscole, è necessario che l'operazione sia indipendente dalle impostazioni cultura in modo che il risultato non venga influenzato dal valore di <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.  
  
 Indipendentemente dal fatto che l'applicazione sviluppata comprenda o meno codice per la gestione dei problemi di localizzazione e globalizzazione, è opportuno tenere in considerazione i metodi di .NET Framework che per impostazione predefinita recuperano risultati dipendenti dalle impostazioni cultura. Il presente argomento ha lo scopo di illustrare il corretto utilizzo di tali metodi da parte delle applicazioni per ottenere risultati indipendenti dalle impostazioni cultura.  
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)
