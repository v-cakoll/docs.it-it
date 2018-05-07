---
title: Risoluzione dei problemi relativi ai provider di tipi
description: 'Individuare possibili soluzioni per i problemi che si sono più probabile che si verifichino quando si utilizzano provider di tipi in F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 6dcae0e510d27fb0b07799b4edfe2d5bb9aeb2d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-type-providers"></a>Risoluzione dei problemi relativi ai provider di tipi

In questo argomento descrive e fornisce le potenziali soluzioni per i problemi che si sono più probabile che si verifichino quando si utilizzano provider di tipo.


## <a name="possible-problems-with-type-providers"></a>Problemi con i provider di tipi
Se si verifica un problema quando si lavora con i provider di tipi, è possibile esaminare la tabella seguente per le soluzioni più comuni.



|Problema|Azioni consigliate|
|-------|-----------------|
|**Le modifiche dello schema**. Tipo di provider lavoro meglio quando lo schema di origine dati è stabile. Se si aggiunge una tabella di dati o di una colonna o un'altra modifica a tale schema, il provider di tipi non riconosce automaticamente queste modifiche.|Eliminare o ricompilare il progetto. Per pulire il progetto, scegliere **compilare**, **Pulisci** *ProjectName* nella barra dei menu. Per ricompilare il progetto, scegliere **compilare**, **ricompilare** *ProjectName* nella barra dei menu. Tali azioni reimpostare lo stato di tutti i tipo provider e forzare il provider per ristabilire la connessione all'origine dati e ottenere informazioni sullo schema aggiornato.|
|**Errore di connessione**. La stringa di connessione o l'URL è corretta, la rete è inattiva o l'origine dati o il servizio non è disponibile.|Per un servizio web o un servizio OData, è possibile provare l'URL in Internet Explorer per verificare che l'URL sia corretto e che il servizio è disponibile. Per una stringa di connessione di database, è possibile utilizzare gli strumenti di connessione dati **Esplora Server** per verificare se la stringa di connessione sia valida e il database è disponibile. Dopo aver ripristinato la connessione, è necessario pulire o ricompilare il progetto in modo che il provider di tipi si riconnetterà alla rete.|
|**Credenziali non valide**. È necessario disporre delle autorizzazioni valide per il servizio web o di origine di dati.|Per una connessione SQL, il nome utente e la password specificati nel file di configurazione o stringa di connessione deve essere validi per il database. Se si utilizza l'autenticazione di Windows, è necessario avere accesso al database. L'amministratore del database è possibile identificare le autorizzazioni per che necessarie l'accesso a ogni database e ogni elemento all'interno di un database.<br /><br />Per un servizio web o un servizio dati, è necessario disporre delle credenziali appropriate. La maggior parte dei provider di tipi forniscono un oggetto DataContext, che contiene una proprietà di credenziali che è possibile impostare con la chiave di accesso e il nome utente appropriato.|
|**Percorso non valido**. Un percorso di un file non valido.|Verificare che il percorso sia corretto e che il file esista. Inoltre, è necessario utilizzare le virgolette in modo appropriato con qualsiasi backlashes nel percorso o utilizzare una stringa verbatim o una stringa racchiusa tra virgolette triple.|

## <a name="see-also"></a>Vedere anche
[Provider di tipi](index.md)
