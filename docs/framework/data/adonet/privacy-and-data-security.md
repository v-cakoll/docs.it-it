---
title: Privacy e sicurezza dei dati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46fa5839-adf7-4c7c-bce3-71e941fa7de9
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5c645b493a1ffb99f4d60f8011bc05f275b5d10f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="privacy-and-data-security"></a>Privacy e sicurezza dei dati
La salvaguardia e la gestione di informazioni sensibili nelle applicazioni ADO.NET dipendono dai prodotti e dalle tecnologie sottostanti usati per crearle. ADO.NET non fornisce direttamente servizi per la protezione o la crittografia dei dati.  
  
## <a name="cryptography-and-hash-codes"></a>Crittografia e codici hash  
 In .NET Framework le classi nello spazio dei nomi <xref:System.Security.Cryptography> possono essere usate dalle applicazioni ADO.NET per impedire che i dati vengano letti o modificati da terze parti non autorizzate. In alcuni casi si tratta di wrapper presenti nelle CryptoAPI di Microsoft non gestite, in altri semplicemente di implementazioni gestite. Il [servizi di crittografia](http://msdn.microsoft.com/en-us/68a1e844-c63c-44af-9247-f6716eb23781) argomento viene fornita una panoramica della crittografia in .NET Framework, descrive la modalità di implementazione cryptograph e come eseguire specifiche attività di crittografia.  
  
 Diversamente dalla crittografia, che consente di crittografare i dati e di decrittografarli in un secondo momento, l'hash dei dati è un processo irreversibile. Risulta utile quando si desidera impedire la manomissione dei dati verificando che non siano stati alterati. Con stringhe di input identiche, gli algoritmi di hash producono sempre valori di output brevi facilmente confrontabili. [Integrità dei dati con i codici Hash](../../../../docs/standard/security/ensuring-data-integrity-with-hash-codes.md) viene descritto come generare e verificare i valori hash.  
  
## <a name="encrypting-configuration-files"></a>Crittografia dei file di configurazione  
 La protezione dell'accesso all'origine dati è uno dei principali obiettivi da raggiungere quando si imposta la sicurezza di un'applicazione. Una stringa di connessione presenta una potenziale vulnerabilità se non è protetta. Le stringhe di connessione salvate nei file di configurazione vengono archiviate in file XML standard per i quali in .NET Framework è stato definito un set comune di elementi. La configurazione protetta consente di crittografare informazioni sensibili in un file di configurazione. Sebbene sia stata progettata principalmente per applicazioni ASP.NET, questa funzionalità può essere usata anche per crittografare sezioni dei file di configurazione nelle applicazioni Windows. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="securing-string-values-in-memory"></a>Protezione di valori stringa in memoria  
 Se un oggetto <xref:System.String> contiene informazioni sensibili, ad esempio password, numeri di carta di credito o dati personali, vi è il rischio che tali informazioni possano essere rivelate dopo l'uso poiché i dati non vengono eliminati dalla memoria del computer.  
  
 L'oggetto <xref:System.String> non è modificabile, ovvero una volta creato, non è possibile modificarne il valore. Le modifiche che apparentemente modificano il valore stinga in realtà creano una nuova istanza di un oggetto <xref:System.String> in memoria, archiviando i dati come testo normale. Inoltre, non è possibile prevedere in quale momento le istanze della stringa verranno eliminate dalla memoria. Il recupero della memoria con le stringhe non è deterministico con Garbage Collection di .NET. È opportuno evitare di usare le classi <xref:System.String> e <xref:System.Text.StringBuilder> se i dati sono realmente sensibili.  
  
 La classe <xref:System.Security.SecureString> fornisce metodi per crittografare testo usando l'API di protezione dei dati (DPAPI) in memoria. La stringa viene quindi eliminata dalla memoria quando non è più necessaria. Non è disponibile alcun metodo `ToString` per leggere rapidamente il contenuto di un oggetto <xref:System.Security.SecureString>. È possibile inizializzare una nuova istanza di `SecureString` senza valore o passando un puntatore a una matrice di oggetti <xref:System.Char>. È quindi possibile usare i vari metodi della classe per gestire la stringa. Per ulteriori informazioni, scaricare il [applicazione di esempio SecureString](http://go.microsoft.com/fwlink/?LinkId=120418), cui viene illustrato come utilizzare la `SecureString` classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Sicurezza di SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
