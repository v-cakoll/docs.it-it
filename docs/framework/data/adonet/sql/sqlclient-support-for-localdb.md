---
title: Supporto SqlClient per LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 200db3b1014278e711062bcbdff81be8d27c3351
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780786"
---
# <a name="sqlclient-support-for-localdb"></a>Supporto SqlClient per LocalDB
A partire da SQL Server nome in codice Denali, sarà disponibile una versione semplificata di SQL Server, denominata local DB. In questo argomento viene illustrato come connettersi a un database di LocalDB.  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sul database locale, inclusa la modalità di installazione del database locale e la configurazione dell'istanza del database locale, vedere documentazione online di SQL Server.  
  
 Per riepilogare le operazioni che è possibile eseguire con LocalDB:  
  
- Creare e avviare le istanze di LocalDB con sqllocaldb.exe o il file app.config.  
  
- Usare sqlcmd.exe per aggiungere e modificare i database in un'istanza di LocalDB. Ad esempio `sqlcmd -S (localdb)\myinst`.  
  
- Usare la parola chiave della stringa di connessione `AttachDBFilename` per aggiungere un database all'istanza di LocalDB. Quando si usa `AttachDBFilename`, se non si specifica il nome del database con la parola chiave della stringa di connessione `Database` , il database verrà rimosso dall'istanza di LocalDB alla chiusura dell'applicazione.  
  
- Specificare un'istanza di LocalDB nella stringa di connessione. Ad esempio, se il nome dell'istanza è `myInstance`, la stringa di connessione includerà:  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 `User Instance=True` non è consentito quando ci si connette a un database di LocalDB.  
  
 È possibile scaricare LocalDB da [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065). Se si utilizza sqlcmd. exe per modificare i dati nell'istanza del database locale, è necessario disporre di sqlcmd da SQL Server 2012, che è possibile ottenere anche dal Feature Pack SQL Server 2012.  
  
## <a name="programmatically-create-a-named-instance"></a>Creare un'istanza denominata a livello di codice  
 Un'applicazione può creare un'istanza denominata e specificare un database come segue:  
  
- Specificare le istanze di LocalDB da creare nel file app.config, come illustrato di seguito.  Il numero di versione dell'istanza deve essere uguale al numero di versione dell'installazione di LocalDB.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- Specificare il nome dell'istanza mediante la parola chiave della stringa di connessione `server` .  Il nome dell'istanza specificato nella parola chiave della stringa di connessione `server` deve corrispondere a quello specificato nel file app.config.  
  
- Usare la parola chiave della stringa di connessione `AttachDBFilename` per specificare il file con estensione MDF.  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità di SQL Server e ADO.NET](sql-server-features-and-adonet.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
