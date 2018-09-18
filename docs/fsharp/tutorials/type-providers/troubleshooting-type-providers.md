---
title: Risoluzione dei problemi relativi ai provider di tipi
description: 'Individua le potenziali soluzioni per i problemi di cui si sono più probabile incontrare quando si usano provider di tipi in F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f3b8ffdaf615563305b7b84b45a9ed1e066d0dcc
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46007490"
---
# <a name="troubleshooting-type-providers"></a>Risoluzione dei problemi relativi ai provider di tipi

In questo argomento descrive e fornisce le potenziali soluzioni per i problemi di cui si sono più probabile incontrare quando si usano provider di tipi.

## <a name="possible-problems-with-type-providers"></a>Possibili problemi con i provider di tipi

Se si verifica un problema quando si lavora con i provider di tipi, è possibile esaminare la tabella seguente per le soluzioni più comuni.

|Problema|Azioni consigliate|
|-------|-----------------|
|**Le modifiche dello schema**. Tipo provider lavoro migliore quando l'origine dati dello schema è stabile. Se si aggiunge una tabella di dati o una colonna o eseguire un'ulteriore modifica a tale schema, il provider di tipi non riconosce automaticamente tali modifiche.|Fase di pulizia o ricompilare il progetto. Per pulire il progetto, scegliere **compilare**, **Pulisci** *NomeProgetto* nella barra dei menu. Per ricompilare il progetto, scegliere **compilare**, **Ricompila** *NomeProgetto* nella barra dei menu. Queste azioni reimpostare lo stato di tutti i tipo provider e forzare il provider per ristabilire la connessione all'origine dati e ottenere informazioni sullo schema aggiornato.|
|**Errore di connessione**. La stringa di connessione o l'URL è corretta, la rete è inattiva o l'origine dati o il servizio non è disponibile.|Per un servizio web o un servizio OData, è possibile provare l'URL in Internet Explorer per verificare se l'URL sia corretto e che il servizio è disponibile. Per una stringa di connessione di database, è possibile usare gli strumenti di connessione dati **Esplora Server** per verificare se la stringa di connessione sia valida e il database è disponibile. Dopo aver ripristinato la connessione, si dovrebbe quindi pulire o ricompilare il progetto in modo che il provider di tipi si riconnetterà alla rete.|
|**Credenziali non valide**. È necessario disporre delle autorizzazioni valide per il servizio web o origine dati.|Per una connessione SQL, il nome utente e la password specificati nel file di configurazione o stringa di connessione deve essere validi per il database. Se si usa l'autenticazione di Windows, è necessario avere accesso al database. L'amministratore del database può identificare ciò che le autorizzazioni per che necessarie accedere a ogni database e ogni elemento all'interno di un database.<br /><br />Per un servizio web o un servizio dati, è necessario disporre delle credenziali appropriate. La maggior parte dei provider di tipi forniscono un oggetto DataContext, che contiene una proprietà di credenziali che è possibile impostare con il nome utente appropriato e la chiave di accesso.|
|**Percorso non valido**. Un percorso di un file non valido.|Verificare se il percorso sia corretto e il file esista. Inoltre, è necessario racchiudere tra virgolette qualsiasi backlashes nel percorso in modo appropriato oppure usare una stringa verbatim o una stringa racchiusa tra virgolette triple.|

## <a name="see-also"></a>Vedere anche

- [Provider di tipi](index.md)
