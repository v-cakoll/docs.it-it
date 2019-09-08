---
title: Crittografia dei dati in SQL Server
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: 1d185dd121336b62bd66a11bf0cc4253b45ae47e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794256"
---
# <a name="data-encryption-in-sql-server"></a>Crittografia dei dati in SQL Server
In SQL Server sono disponibili funzioni per di crittografia e decrittografia dei dati tramite certificato, chiave asimmetrica o chiave simmetrica. Tutte queste funzionalità vengono gestite in un archivio di certificati interno. Nell'archivio viene usata una gerarchia di crittografia per proteggere i certificati e le chiavi di un livello con il livello superiore nella gerarchia. Quest'area di funzionalità di SQL Server è denominata archivio segreto.  
  
 La modalità più veloce supportata dalle funzioni di crittografia è la crittografia con chiave simmetrica. Questa modalità è adatta per la gestione di grandi volumi di dati. Le chiavi simmetriche possono essere crittografate tramite certificati, password o altre chiavi simmetriche.  
  
## <a name="keys-and-algorithms"></a>Chiavi e algoritmi  
 In SQL Server sono supportati diversi algoritmi di crittografia con chiave simmetrica, tra cui DES, Triple DES, RC2, RC4, RC4 a 128 bit, DESX, AES a 128 bit, AES a 192 bit e AES a 256 bit. Gli algoritmi sono implementati usando CryptoAPI di Windows.  
  
 All'interno dell'ambito di una connessione al database, SQL Server consente di mantenere più chiavi simmetriche aperte. Una chiave aperta viene recuperata dall'archivio ed è disponibile per la decrittografia dei dati. Quando un dato viene decrittografato, non è necessario specificare la chiave simmetrica da usare. Ogni valore crittografato contiene l'identificatore della chiave (GUID chiave) usata per crittografarlo. Il motore fa corrispondere il flusso di byte crittografati con una chiave simmetrica aperta, se la chiave corretta è stata decrittografata ed è aperta. La chiave viene quindi usata per eseguire la decrittografia e restituire i dati. Se non viene aperta la chiave corretta, viene restituito Null.  
  
 Per un esempio in cui viene illustrato come utilizzare i dati crittografati in un database, vedere [crittografare una colonna di dati](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni sulla crittografia dei dati, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|-|-|  
|[Crittografia SQL Server](/sql/relational-databases/security/encryption/sql-server-encryption)|Viene fornita una panoramica della crittografia in SQL Server. Questo argomento include i collegamenti ad altri articoli.|  
|[Gerarchia di crittografia](/sql/relational-databases/security/encryption/encryption-hierarchy)|Viene fornita una panoramica della crittografia in SQL Server. In questo argomento vengono forniti collegamenti ad altri articoli.|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Autenticazione in SQL Server](authentication-in-sql-server.md)
- [Ruoli server e database in SQL Server](server-and-database-roles-in-sql-server.md)
- [Proprietà e separazione tra schemi e utenti in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Autorizzazioni in SQL Server](authorization-and-permissions-in-sql-server.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
