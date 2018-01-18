---
title: Supporto SqlClient per LocalDB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3d643ac386aebf51673f937b3f47e73c749b78f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="sqlclient-support-for-localdb"></a>Supporto SqlClient per LocalDB
A partire da [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] , nome in codice Denali, è disponibile una versione semplificata di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], chiamata LocalDB. In questo argomento viene illustrato come connettersi a un database di LocalDB.  
  
## <a name="remarks"></a>Note  
 Per altre informazioni su LocalDB, ad esempio come installarlo e configurare l'istanza di LocalDB, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] .  
  
 Per riepilogare le operazioni che è possibile eseguire con LocalDB:  
  
-   Creare e avviare le istanze di LocalDB con sqllocaldb.exe o il file app.config.  
  
-   Usare sqlcmd.exe per aggiungere e modificare i database in un'istanza di LocalDB. Ad esempio `sqlcmd -S (localdb)\myinst`.  
  
-   Usare la parola chiave della stringa di connessione `AttachDBFilename` per aggiungere un database all'istanza di LocalDB. Quando si usa `AttachDBFilename`, se non si specifica il nome del database con la parola chiave della stringa di connessione `Database` , il database verrà rimosso dall'istanza di LocalDB alla chiusura dell'applicazione.  
  
-   Specificare un'istanza di LocalDB nella stringa di connessione. Ad esempio, se il nome dell'istanza è `myInstance`, la stringa di connessione includerà:  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 `User Instance=True` non è consentito quando ci si connette a un database di LocalDB.  
  
 È possibile scaricare LocalDB da [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065). Se si usa sqlcmd.exe per modificare i dati nell'istanza di LocalDB, sarà necessario sqlcmd da [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, che è possibile ottenere da [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack.  
  
## <a name="programmatically-create-a-named-instance"></a>Creare un'istanza denominata a livello di codice  
 Un'applicazione può creare un'istanza denominata e specificare un database come segue:  
  
-   Specificare le istanze di LocalDB da creare nel file app.config, come illustrato di seguito.  Il numero di versione dell'istanza deve essere uguale al numero di versione dell'installazione di LocalDB.  
  
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
  
-   Specificare il nome dell'istanza mediante la parola chiave della stringa di connessione `server` .  Il nome dell'istanza specificato nella parola chiave della stringa di connessione `server` deve corrispondere a quello specificato nel file app.config.  
  
-   Usare la parola chiave della stringa di connessione `AttachDBFilename` per specificare il file con estensione MDF.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità di SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
