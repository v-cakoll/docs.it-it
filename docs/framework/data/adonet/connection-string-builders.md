---
title: Generatori di stringhe di connessione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a782969502509cb766e3a1d38222118a352dc3db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="connection-string-builders"></a><span data-ttu-id="59d3c-102">Generatori di stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="59d3c-102">Connection String Builders</span></span>
<span data-ttu-id="59d3c-103">Nelle versioni precedenti di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], controllo delle stringhe di connessione con la stringa concatenata valori non è stata eseguita, in modo che in fase di esecuzione, una parola chiave non generato in fase di compilazione un <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="59d3c-103">In earlier versions of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="59d3c-104">Poiché ogni provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] supporta una sintassi diversa per le parole chiave delle stringhe di connessione, la costruzione manuale di stringhe di connessione valide risulta difficile.</span><span class="sxs-lookup"><span data-stu-id="59d3c-104">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="59d3c-105">Per risolvere questo problema, in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 sono stati introdotti nuovi generatori di stringhe di connessione per ogni provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59d3c-105">To address this problem, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 introduced new connection string builders for each [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="59d3c-106">Ogni provider di dati include una classe di generatori di stringhe di connessione fortemente tipizzata che eredita da <xref:System.Data.Common.DbConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="59d3c-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="59d3c-107">Nella tabella seguente sono elencati i provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] e le classi di compilatori di stringhe di connessione associate.</span><span class="sxs-lookup"><span data-stu-id="59d3c-107">The following table lists the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="59d3c-108">Provider</span><span class="sxs-lookup"><span data-stu-id="59d3c-108">Provider</span></span>|<span data-ttu-id="59d3c-109">Classe ConnectionStringBuilder</span><span class="sxs-lookup"><span data-stu-id="59d3c-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="59d3c-110">Attacchi injection alle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="59d3c-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="59d3c-111">Un attacco injection alle stringhe di connessione può verificarsi quando si usa la concatenazione dinamica di stringhe per compilare stringhe di connessione basate sull'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59d3c-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="59d3c-112">Se la stringa non viene convalidata e il testo o i caratteri dannosi non vengono convertiti in caratteri di escape, un utente non autorizzato potrebbe accedere a dati sensibili o ad altre risorse del server.</span><span class="sxs-lookup"><span data-stu-id="59d3c-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="59d3c-113">Ad esempio, un utente non autorizzato potrebbe eseguire un attacco specificando un punto e virgola e aggiungendo un altro valore.</span><span class="sxs-lookup"><span data-stu-id="59d3c-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="59d3c-114">La stringa di connessione viene analizzata tramite un algoritmo basato sul principio che l'ultima occorrenza ha la priorità, pertanto l'input dannoso viene sostituito a un valore lecito.</span><span class="sxs-lookup"><span data-stu-id="59d3c-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="59d3c-115">Le classi di generatori di stringhe di connessione sono progettate per eliminare la necessità di basarsi su congetture e proteggersi da errori di sintassi e vulnerabilità della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="59d3c-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="59d3c-116">Forniscono metodi e proprietà che corrispondono alle coppie chiave/valore note consentite da ogni provider di dati.</span><span class="sxs-lookup"><span data-stu-id="59d3c-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="59d3c-117">Ogni classe mantiene una raccolta fissa di sinonimi e può essere convertita da un sinonimo al nome di chiave noto.</span><span class="sxs-lookup"><span data-stu-id="59d3c-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="59d3c-118">Vengono eseguiti controlli per rilevare coppie chiave/valore valide e le coppie non valide generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="59d3c-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="59d3c-119">Inoltre, i valori inseriti vengono gestiti in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="59d3c-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="59d3c-120">Nell'esempio seguente viene illustrata la modalità con cui <xref:System.Data.SqlClient.SqlConnectionStringBuilder> gestisce un valore aggiuntivo inserito per l'impostazione `Initial Catalog`.</span><span class="sxs-lookup"><span data-stu-id="59d3c-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 <span data-ttu-id="59d3c-121">Dall'output si rileva che <xref:System.Data.SqlClient.SqlConnectionStringBuilder> ha gestito correttamente questa situazione convertendo in caratteri di escape il valore aggiuntivo in virgolette doppie anziché aggiungerlo alla stringa di connessione come nuova coppia chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="59d3c-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="59d3c-122">Compilazione di stringhe di connessione da file di configurazione</span><span class="sxs-lookup"><span data-stu-id="59d3c-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="59d3c-123">Se determinati elementi di una stringa di connessione sono noti in anticipo, possono essere archiviati in un file di configurazione e recuperati in fase di esecuzione per costruire una stringa di connessione completa.</span><span class="sxs-lookup"><span data-stu-id="59d3c-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="59d3c-124">Ad esempio, è possibile che il nome del database sia noto in anticipo, ma non il nome del server.</span><span class="sxs-lookup"><span data-stu-id="59d3c-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="59d3c-125">Oppure è possibile che si desideri che un utente specifichi un nome utente e una password in fase di esecuzione senza avere la possibilità di inserire altri valori nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="59d3c-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="59d3c-126">Uno dei costruttori di overload per un generatore di stringhe di connessione accetta <xref:System.String> come argomento, consentendo di specificare una stringa di connessione parziale che può essere quindi completata dall'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59d3c-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="59d3c-127">La stringa di connessione parziale può essere archiviata in un file di configurazione e recuperata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="59d3c-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59d3c-128">Lo spazio dei nomi <xref:System.Configuration> consente l'accesso a livello di codice ai file di configurazione che usano <xref:System.Web.Configuration.WebConfigurationManager> per le applicazioni Web e <xref:System.Configuration.ConfigurationManager> per le applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="59d3c-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="59d3c-129">Per ulteriori informazioni sull'utilizzo delle stringhe di connessione e i file di configurazione, vedere [stringhe di connessione e i file di configurazione](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="59d3c-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="59d3c-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="59d3c-130">Example</span></span>  
 <span data-ttu-id="59d3c-131">In questo esempio vengono illustrati il recupero di una stringa di connessione da un file di configurazione e il relativo completamento tramite l'impostazione delle proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> e <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> di <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="59d3c-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="59d3c-132">Il file di configurazione viene definito come segue.</span><span class="sxs-lookup"><span data-stu-id="59d3c-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="59d3c-133">È necessario impostare un riferimento a `System.Configuration.dll` nel progetto affinché il codice venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="59d3c-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="59d3c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59d3c-134">See Also</span></span>  
 [<span data-ttu-id="59d3c-135">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="59d3c-135">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="59d3c-136">Privacy e sicurezza dei dati</span><span class="sxs-lookup"><span data-stu-id="59d3c-136">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [<span data-ttu-id="59d3c-137">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="59d3c-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
