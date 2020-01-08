---
title: Privacy e sicurezza dei dati
ms.date: 03/30/2017
ms.assetid: 46fa5839-adf7-4c7c-bce3-71e941fa7de9
ms.openlocfilehash: a8d7ae2ece966b4649c9c988c123304fe3f1b4d9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348130"
---
# <a name="privacy-and-data-security"></a>Privacy e sicurezza dei dati
La salvaguardia e la gestione di informazioni sensibili nelle applicazioni ADO.NET dipendono dai prodotti e dalle tecnologie sottostanti usati per crearle. ADO.NET non fornisce direttamente servizi per la protezione o la crittografia dei dati.  
  
## <a name="cryptography-and-hash-codes"></a>Crittografia e codici hash  
 In .NET Framework le classi nello spazio dei nomi <xref:System.Security.Cryptography> possono essere usate dalle applicazioni ADO.NET per impedire che i dati vengano letti o modificati da terze parti non autorizzate. In alcuni casi si tratta di wrapper presenti nelle CryptoAPI di Microsoft non gestite, in altri semplicemente di implementazioni gestite. Nell'argomento relativo ai [servizi di crittografia](../../../standard/security/cryptographic-services.md) viene fornita una panoramica della crittografia nell'.NET Framework, viene descritto come viene implementata la crittografia e viene illustrato come eseguire specifiche attività di crittografia.  
  
 Diversamente dalla crittografia, che consente di crittografare i dati e di decrittografarli in un secondo momento, l'hash dei dati è un processo irreversibile. Risulta utile quando si desidera impedire la manomissione dei dati verificando che non siano stati alterati. Con stringhe di input identiche, gli algoritmi di hash producono sempre valori di output brevi facilmente confrontabili. [Garantendo l'integrità dei dati con i codici hash](../../../standard/security/ensuring-data-integrity-with-hash-codes.md) viene descritto come generare e verificare i valori hash.  
  
## <a name="encrypting-configuration-files"></a>Crittografia dei file di configurazione  
 La protezione dell'accesso all'origine dati è uno dei principali obiettivi da raggiungere quando si imposta la sicurezza di un'applicazione. Se non protetta, una stringa di connessione presenta una potenziale vulnerabilità. Le stringhe di connessione salvate nei file di configurazione vengono archiviate in file XML standard per i quali in .NET Framework è stato definito un set comune di elementi. La configurazione protetta consente di crittografare informazioni sensibili in un file di configurazione. Sebbene sia stata progettata principalmente per applicazioni ASP.NET, questa funzionalità può essere usata anche per crittografare sezioni dei file di configurazione nelle applicazioni Windows. Per altre informazioni, vedere [Protezione delle informazioni di connessione](protecting-connection-information.md).  
  
## <a name="securing-string-values-in-memory"></a>Protezione di valori stringa in memoria  
 Se un oggetto <xref:System.String> contiene informazioni sensibili, ad esempio password, numeri di carta di credito o dati personali, vi è il rischio che tali informazioni possano essere rivelate dopo l'uso poiché i dati non vengono eliminati dalla memoria del computer.  
  
 L'oggetto <xref:System.String> non è modificabile, ovvero una volta creato, non è possibile modificarne il valore. Le modifiche che apparentemente modificano il valore stinga in realtà creano una nuova istanza di un oggetto <xref:System.String> in memoria, archiviando i dati come testo normale. Inoltre, non è possibile prevedere in quale momento le istanze della stringa verranno eliminate dalla memoria. Il recupero della memoria con le stringhe non è deterministico con Garbage Collection di .NET. È opportuno evitare di usare le classi <xref:System.String> e <xref:System.Text.StringBuilder> se i dati sono realmente sensibili.  
  
 La classe <xref:System.Security.SecureString> fornisce metodi per crittografare testo usando l'API di protezione dei dati (DPAPI) in memoria. La stringa viene quindi eliminata dalla memoria quando non è più necessaria. Non è disponibile alcun metodo `ToString` per leggere rapidamente il contenuto di un oggetto <xref:System.Security.SecureString>. È possibile inizializzare una nuova istanza di `SecureString` senza valore o passando un puntatore a una matrice di oggetti <xref:System.Char>. È quindi possibile usare i vari metodi della classe per gestire la stringa.
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](securing-ado-net-applications.md)
- [Sicurezza di SQL Server](./sql/sql-server-security.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
