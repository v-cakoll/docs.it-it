---
ms.openlocfilehash: 1f06a185939c40274adad1ceac6990719069167a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235655"
---
### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Modifica del comportamento nelle API DDL (Data Definition Language)

|   |   |
|---|---|
|Dettagli|Il comportamento delle API DDL quando si specifica AttachDBFilename è cambiato come segue:<ul><li>Le stringhe di connessione non devono specificare un valore Initial Catalog. In precedenza, erano necessari sia AttachDBFilename che Initial Catalog.</li><li>Se vengono specificati sia AttachDBFilename che il catalogo iniziale e il file MDF indicato esiste, il metodo <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> restituisce <code>true</code>. In precedenza, restituiva <code>false</code>.</li><li>Se vengono specificati sia AttachDBFilename che il catalogo iniziale e il file MDF indicato esiste, la chiamata del metodo <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> elimina i file.</li><li>Se <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> viene chiamato quando la stringa di connessione specifica un valore AttachDBFilename con un file MDF e un catalogo iniziale inesistenti, il metodo genera un'eccezione <xref:System.InvalidOperationException>. In precedenza, generava un'eccezione <xref:System.Data.SqlClient.SqlException>.</li></ul>|
|Suggerimento|Queste modifiche semplificano la creazione di strumenti e applicazioni che usano le API DDL. Tali modifiche possono influire sulla compatibilità delle applicazioni negli scenari seguenti:<ul><li>L'utente scrive codice che esegue un comando <code>DROP DATABASE</code> direttamente anziché chiamando <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> se <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> restituisce <code>true</code>. Questa operazione interrompe il codice esistente se il database non è collegato ma il file MDF esiste.</li><li>L'utente scrive codice che prevede che il metodo <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> generi un'eccezione <xref:System.Data.SqlClient.SqlException> anziché un'eccezione <xref:System.InvalidOperationException> se il catalogo iniziale e il file MDF non esistono.</li></ul>|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
