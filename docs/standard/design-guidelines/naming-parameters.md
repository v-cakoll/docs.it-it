---
title: Denominazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: ebe2e2db4b109057bf576d4e18cfe511c657707e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743835"
---
# <a name="naming-parameters"></a>Denominazione di parametri
Oltre al motivo più ovvio della leggibilità, è importante seguire le linee guida per i nomi dei parametri, perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visivi forniscono funzionalità IntelliSense e di esplorazione delle classi.

 ✔️ utilizzare camelCasing nei nomi dei parametri.

 ✔️ utilizzare nomi di parametro descrittivi.

 ✔️ CONSIDERARE l'uso di nomi basati sul significato di un parametro anziché sul tipo del parametro.

### <a name="naming-operator-overload-parameters"></a>Denominazione dei parametri di overload degli operatori
 ✔️ utilizzare `left` e `right` per i nomi dei parametri di overload degli operatori binari se non esiste alcun significato per i parametri.

 ✔️ usare `value` per i nomi dei parametri di overload dell'operatore unario se non esiste alcun significato per i parametri.

 ✔️ CONSIDERARE nomi significativi per i parametri di overload degli operatori se questa operazione aggiunge un valore significativo.

 ❌ non utilizzano abbreviazioni o indici numerici per i nomi dei parametri di overload degli operatori.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
