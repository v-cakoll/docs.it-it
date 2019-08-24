---
title: Errori in fase di progettazione in Progettazione Windows Form
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015964"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Errori della fase di progettazione nel Progettazione Windows Form

Questo argomento illustra il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Visual Studio quando non è possibile caricare il Progettazione Windows Form. Se viene visualizzato questo elenco di errori non si deve interpretarlo come un bug della progettazione, ma come ausilio per la correzione degli errori nel codice.

Una conoscenza di base di questo elenco di errori consentirà di eseguire il debug delle applicazioni fornendo informazioni dettagliate sugli errori e suggerendo le possibili soluzioni.

## <a name="the-design-time-error-list-interface"></a>Interfaccia elenco errori in fase di progettazione

Se non è possibile caricare il Progettazione Windows Form, nella finestra di progettazione viene visualizzato un elenco errori. Gli errori sono raggruppati in categorie. Ad esempio, se si dispone di quattro istanze di variabili non dichiarate, queste verranno raggruppate nella stessa categoria di errori. Ogni categoria di errori include una breve descrizione che riepiloga l'errore.

È possibile espandere o comprimere una categoria di errore facendo clic sull'intestazione della categoria di errori oppure facendo clic sulla freccia di espansione di espansione/compressione. Quando si espande una categoria di errori, vengono visualizzate le seguenti informazioni aggiuntive:

- Istanze dell'errore.

- Informazioni sull'errore.

- Post dei forum sull'errore.

### <a name="instances-of-this-error"></a>Istanze dell'errore

Nelle informazioni sono elencate tutte le istanze dell'errore nel progetto corrente. Molti errori evidenziano un percorso esatto nel formato seguente: *[nome progetto]* *[nome modulo]* riga: *[numero riga]* colonna: *[numero colonna]* . Il collegamento **Vai al codice** consente di visualizzare il percorso nel codice in cui si verifica l'errore.

Se uno stack di chiamate è associato all'errore, è possibile selezionare il collegamento **Mostra stack di chiamate** che espande ulteriormente l'errore per visualizzare lo stack di chiamate. L'analisi dello stack può fornire informazioni utili sul debug. Ad esempio, è possibile rilevare le funzioni chiamate prima del verificarsi dell'errore. Lo stack di chiamate è selezionabile, in modo da poterlo copiare e salvare.

> [!NOTE]
> In Visual Basic l'elenco degli errori in fase di progettazione non mostra più di un errore, ma è possibile visualizzare più istanze dello stesso errore. In Visual C++ gli errori non sono dotati di collegamenti per andare al codice o al numero di riga.

### <a name="forum-posts-about-this-error"></a>Post dei forum sull'errore

La Guida aggiuntiva include un collegamento ai post del forum relativi all'errore. La ricerca viene effettuata nei forum sulla base della stringa del messaggio di errore. È anche possibile provare a eseguire ricerche nei forum seguenti:

- [Forum Progettazione Windows Form](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [Forum Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a>Ignora e continua

È possibile ignorare la condizione di errore e continuare a caricare la finestra di progettazione. La scelta di questa azione può produrre risultati imprevisti. Ad esempio, nell'area di progettazione potrebbero non venire visualizzati alcuni controlli.

## <a name="see-also"></a>Vedere anche

- [Risoluzione dei problemi di sviluppo in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [Risoluzione dei problemi relativi alla modifica di controlli e componenti](troubleshooting-control-and-component-authoring.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Messaggi di errore di Progettazione Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))
