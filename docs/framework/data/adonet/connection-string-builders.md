---
title: Generatori di stringhe di connessione
description: Informazioni sulle classi del generatore di stringhe di connessione usate per diversi provider in ADO.NET, che ereditano tutti da DbConnectionStringBuilder.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: e493140b4cf5a939e8ae8f42b617fb739ed09dec
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287064"
---
# <a name="connection-string-builders"></a><span data-ttu-id="b922f-103">Generatori di stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="b922f-103">Connection String Builders</span></span>
<span data-ttu-id="b922f-104">Nelle versioni precedenti di ADO.NET, il controllo in fase di compilazione delle stringhe di connessione con valori di stringa concatenati non è stato eseguito, in modo che, in fase di esecuzione, una parola chiave non corretta abbia generato un oggetto <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="b922f-104">In earlier versions of ADO.NET, compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="b922f-105">Ogni provider di dati .NET Framework supportava una sintassi diversa per le parole chiave della stringa di connessione, rendendo difficoltosa la costruzione di stringhe di connessione valide se effettuate manualmente.</span><span class="sxs-lookup"><span data-stu-id="b922f-105">Each of the .NET Framework data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="b922f-106">Per risolvere questo problema, in ADO.NET 2,0 sono stati introdotti nuovi generatori di stringhe di connessione per ogni provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b922f-106">To address this problem, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="b922f-107">Ogni provider di dati include una classe di generatori di stringhe di connessione fortemente tipizzata che eredita da <xref:System.Data.Common.DbConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="b922f-107">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="b922f-108">Nella tabella seguente sono elencati i provider di dati .NET Framework e le classi del generatore di stringhe di connessione associate.</span><span class="sxs-lookup"><span data-stu-id="b922f-108">The following table lists the .NET Framework data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="b922f-109">Provider</span><span class="sxs-lookup"><span data-stu-id="b922f-109">Provider</span></span>|<span data-ttu-id="b922f-110">Classe ConnectionStringBuilder</span><span class="sxs-lookup"><span data-stu-id="b922f-110">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="b922f-111">Attacchi injection alle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="b922f-111">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="b922f-112">Un attacco injection alle stringhe di connessione può verificarsi quando si usa la concatenazione dinamica di stringhe per compilare stringhe di connessione basate sull'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b922f-112">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="b922f-113">Se la stringa non viene convalidata e il testo o i caratteri dannosi non vengono convertiti in caratteri di escape, un utente non autorizzato potrebbe accedere a dati sensibili o ad altre risorse del server.</span><span class="sxs-lookup"><span data-stu-id="b922f-113">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="b922f-114">Ad esempio, un utente non autorizzato potrebbe eseguire un attacco specificando un punto e virgola e aggiungendo un altro valore.</span><span class="sxs-lookup"><span data-stu-id="b922f-114">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="b922f-115">La stringa di connessione viene analizzata tramite un algoritmo basato sul principio che l'ultima occorrenza ha la priorità, pertanto l'input dannoso viene sostituito a un valore lecito.</span><span class="sxs-lookup"><span data-stu-id="b922f-115">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="b922f-116">Le classi di generatori di stringhe di connessione sono progettate per eliminare la necessità di basarsi su congetture e proteggersi da errori di sintassi e vulnerabilità della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b922f-116">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="b922f-117">Forniscono metodi e proprietà che corrispondono alle coppie chiave/valore note consentite da ogni provider di dati.</span><span class="sxs-lookup"><span data-stu-id="b922f-117">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="b922f-118">Ogni classe mantiene una raccolta fissa di sinonimi e può essere convertita da un sinonimo al nome di chiave noto.</span><span class="sxs-lookup"><span data-stu-id="b922f-118">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="b922f-119">Vengono eseguiti controlli per rilevare coppie chiave/valore valide e le coppie non valide generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b922f-119">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="b922f-120">Inoltre, i valori inseriti vengono gestiti in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="b922f-120">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="b922f-121">Nell'esempio seguente viene illustrata la modalità con cui <xref:System.Data.SqlClient.SqlConnectionStringBuilder> gestisce un valore aggiuntivo inserito per l'impostazione `Initial Catalog`.</span><span class="sxs-lookup"><span data-stu-id="b922f-121">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
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
  
 <span data-ttu-id="b922f-122">Dall'output si rileva che <xref:System.Data.SqlClient.SqlConnectionStringBuilder> ha gestito correttamente questa situazione convertendo in caratteri di escape il valore aggiuntivo in virgolette doppie anziché aggiungerlo alla stringa di connessione come nuova coppia chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="b922f-122">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```output  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="b922f-123">Compilazione di stringhe di connessione da file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b922f-123">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="b922f-124">Se determinati elementi di una stringa di connessione sono noti in anticipo, possono essere archiviati in un file di configurazione e recuperati in fase di esecuzione per costruire una stringa di connessione completa.</span><span class="sxs-lookup"><span data-stu-id="b922f-124">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="b922f-125">Ad esempio, è possibile che il nome del database sia noto in anticipo, ma non il nome del server.</span><span class="sxs-lookup"><span data-stu-id="b922f-125">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="b922f-126">Oppure è possibile che si desideri che un utente specifichi un nome utente e una password in fase di esecuzione senza avere la possibilità di inserire altri valori nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="b922f-126">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="b922f-127">Uno dei costruttori di overload per un generatore di stringhe di connessione accetta <xref:System.String> come argomento, consentendo di specificare una stringa di connessione parziale che può essere quindi completata dall'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b922f-127">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="b922f-128">La stringa di connessione parziale può essere archiviata in un file di configurazione e recuperata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b922f-128">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b922f-129">Lo spazio dei nomi <xref:System.Configuration> consente l'accesso a livello di codice ai file di configurazione che usano <xref:System.Web.Configuration.WebConfigurationManager> per le applicazioni Web e <xref:System.Configuration.ConfigurationManager> per le applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="b922f-129">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="b922f-130">Per ulteriori informazioni sull'utilizzo delle stringhe di connessione e dei file di configurazione, vedere [stringhe di connessione e file di configurazione](connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="b922f-130">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="b922f-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="b922f-131">Example</span></span>  
 <span data-ttu-id="b922f-132">In questo esempio vengono illustrati il recupero di una stringa di connessione da un file di configurazione e il relativo completamento tramite l'impostazione delle proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> e <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> di <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="b922f-132">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="b922f-133">Il file di configurazione viene definito come segue.</span><span class="sxs-lookup"><span data-stu-id="b922f-133">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> <span data-ttu-id="b922f-134">È necessario impostare un riferimento a `System.Configuration.dll` nel progetto affinché il codice venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="b922f-134">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b922f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b922f-135">See also</span></span>

- [<span data-ttu-id="b922f-136">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="b922f-136">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="b922f-137">Privacy e sicurezza dei dati</span><span class="sxs-lookup"><span data-stu-id="b922f-137">Privacy and Data Security</span></span>](privacy-and-data-security.md)
- [<span data-ttu-id="b922f-138">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b922f-138">ADO.NET Overview</span></span>](ado-net-overview.md)
