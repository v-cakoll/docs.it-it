---
title: Supporto SqlClient per LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 416945964af7fda5ed5aaab2f5aae1bbc8928556
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204757"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="2cfd5-102">Supporto SqlClient per LocalDB</span><span class="sxs-lookup"><span data-stu-id="2cfd5-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="2cfd5-103">A partire da SQL Server nome in codice Denali, una versione leggera di SQL Server, chiamata LocalDB, sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="2cfd5-104">In questo argomento viene illustrato come connettersi a un database di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cfd5-105">Note</span><span class="sxs-lookup"><span data-stu-id="2cfd5-105">Remarks</span></span>  
 <span data-ttu-id="2cfd5-106">Per ulteriori informazioni su LocalDB, incluse le procedure per installarlo e configurare l'istanza di Local DB, vedere la documentazione Online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="2cfd5-107">Per riepilogare le operazioni che è possibile eseguire con LocalDB:</span><span class="sxs-lookup"><span data-stu-id="2cfd5-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="2cfd5-108">Creare e avviare le istanze di LocalDB con sqllocaldb.exe o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="2cfd5-109">Usare sqlcmd.exe per aggiungere e modificare i database in un'istanza di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="2cfd5-110">Ad esempio `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="2cfd5-111">Usare la parola chiave della stringa di connessione `AttachDBFilename` per aggiungere un database all'istanza di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="2cfd5-112">Quando si usa `AttachDBFilename`, se non si specifica il nome del database con la parola chiave della stringa di connessione `Database` , il database verrà rimosso dall'istanza di LocalDB alla chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="2cfd5-113">Specificare un'istanza di LocalDB nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="2cfd5-114">Ad esempio, se il nome dell'istanza è `myInstance`, la stringa di connessione includerà:</span><span class="sxs-lookup"><span data-stu-id="2cfd5-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="2cfd5-115">`User Instance=True` non è consentito quando ci si connette a un database di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="2cfd5-116">È possibile scaricare LocalDB da [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="2cfd5-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="2cfd5-117">Se si utilizzerà sqlcmd.exe per modificare i dati nell'istanza di LocalDB, sarà necessario sqlcmd da SQL Server 2012, è anche possibile ottenere dal Feature Pack di SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="2cfd5-118">Creare un'istanza denominata a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2cfd5-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="2cfd5-119">Un'applicazione può creare un'istanza denominata e specificare un database come segue:</span><span class="sxs-lookup"><span data-stu-id="2cfd5-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="2cfd5-120">Specificare le istanze di LocalDB da creare nel file app.config, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="2cfd5-121">Il numero di versione dell'istanza deve essere uguale al numero di versione dell'installazione di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
-   <span data-ttu-id="2cfd5-122">Specificare il nome dell'istanza mediante la parola chiave della stringa di connessione `server` .</span><span class="sxs-lookup"><span data-stu-id="2cfd5-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="2cfd5-123">Il nome dell'istanza specificato nella parola chiave della stringa di connessione `server` deve corrispondere a quello specificato nel file app.config.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="2cfd5-124">Usare la parola chiave della stringa di connessione `AttachDBFilename` per specificare il file con estensione MDF.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfd5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cfd5-125">See also</span></span>

- [<span data-ttu-id="2cfd5-126">Funzionalità di SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2cfd5-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)
- [<span data-ttu-id="2cfd5-127">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="2cfd5-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
