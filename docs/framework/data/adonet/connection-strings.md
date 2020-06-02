---
title: Stringhe di connessione
description: Informazioni sulle stringhe di connessione in ADO.NET, che contengono informazioni di inizializzazione passate come parametro da un provider di dati a un'origine dati.
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: baa6599a532746895cbb3920f2c623dd4c2be864
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287025"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="d0c68-103">Stringhe di connessione in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d0c68-103">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="d0c68-104">Una stringa di connessione contiene informazioni di inizializzazione che vengono passate come parametro da un provider di dati a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="d0c68-105">Il provider di dati riceve la stringa di connessione come valore della <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0c68-105">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d0c68-106">Il provider analizza la stringa di connessione e garantisce che la sintassi sia corretta e che le parole chiave siano supportate.</span><span class="sxs-lookup"><span data-stu-id="d0c68-106">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="d0c68-107">Quindi il <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> metodo passa i parametri di connessione analizzati all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-107">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="d0c68-108">L'origine dati esegue una convalida ulteriore e stabilisce una connessione.</span><span class="sxs-lookup"><span data-stu-id="d0c68-108">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="d0c68-109">Sintassi delle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="d0c68-109">Connection string syntax</span></span>

<span data-ttu-id="d0c68-110">Una stringa di connessione è un elenco delimitato da punti e virgola di coppie di parametri chiave/valore:</span><span class="sxs-lookup"><span data-stu-id="d0c68-110">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="d0c68-111">Le parole chiave non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d0c68-111">Keywords are not case-sensitive.</span></span> <span data-ttu-id="d0c68-112">I valori, tuttavia, possono fare distinzione tra maiuscole e minuscole, a seconda dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-112">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="d0c68-113">Sia le parole chiave che i valori possono contenere [spazi vuoti](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="d0c68-113">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="d0c68-114">Gli spazi vuoti iniziali e finali vengono ignorati nelle parole chiave e nei valori non racchiusi tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="d0c68-114">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="d0c68-115">Se un valore contiene il punto e virgola, i [caratteri di controllo Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters)o gli spazi vuoti iniziali o finali, è necessario racchiuderlo tra virgolette singole o doppie.</span><span class="sxs-lookup"><span data-stu-id="d0c68-115">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="d0c68-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d0c68-116">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="d0c68-117">Il carattere di inclusione potrebbe non essere presente nel valore che racchiude.</span><span class="sxs-lookup"><span data-stu-id="d0c68-117">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="d0c68-118">Pertanto, un valore contenente virgolette singole può essere racchiuso tra virgolette doppie e viceversa:</span><span class="sxs-lookup"><span data-stu-id="d0c68-118">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="d0c68-119">È anche possibile utilizzare un carattere di escape per il carattere di inclusione utilizzandone due:</span><span class="sxs-lookup"><span data-stu-id="d0c68-119">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="d0c68-120">Le virgolette stesse, così come il segno di uguale, non richiedono l'escape, quindi sono valide le seguenti stringhe di connessione:</span><span class="sxs-lookup"><span data-stu-id="d0c68-120">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="d0c68-121">Poiché ogni valore viene letto fino al punto e virgola successivo o alla fine della stringa, il valore nel secondo esempio è `a=b=c` e il punto e virgola finale è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d0c68-121">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="d0c68-122">Tutte le stringhe di connessione condividono la stessa sintassi di base descritta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d0c68-122">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="d0c68-123">Il set di parole chiave riconosciute dipende tuttavia dal provider e si è evoluto negli anni dalle API precedenti, ad esempio *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="d0c68-123">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="d0c68-124">Il provider di dati *.NET Framework* per *SQL Server* ( `SqlClient` ) supporta molte parole chiave delle API precedenti, ma è in genere più flessibile e accetta sinonimi per molte delle parole chiave comuni della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="d0c68-124">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="d0c68-125">La digitazione degli errori può causare errori.</span><span class="sxs-lookup"><span data-stu-id="d0c68-125">Typing mistakes can cause errors.</span></span> <span data-ttu-id="d0c68-126">Ad esempio, `Integrated Security=true` è valido, ma `IntegratedSecurity=true` genera un errore.</span><span class="sxs-lookup"><span data-stu-id="d0c68-126">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="d0c68-127">Le stringhe di connessione costruite manualmente in fase di esecuzione dall'input dell'utente non convalidato sono vulnerabili agli attacchi di stringa Injection e compromettono la sicurezza nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-127">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="d0c68-128">Per risolvere questi problemi, in *ADO.NET* 2,0 sono stati introdotti i [generatori di stringhe di connessione](connection-string-builders.md) per ogni provider di dati *.NET Framework* .</span><span class="sxs-lookup"><span data-stu-id="d0c68-128">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="d0c68-129">Questi generatori di stringhe di connessione espongono parametri come proprietà fortemente tipizzate e rendono possibile la convalida della stringa di connessione prima che venga inviata all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-129">These connection string builders expose parameters as strongly typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d0c68-130">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d0c68-130">In This Section</span></span>

<span data-ttu-id="d0c68-131">[Generatori di stringhe di connessione](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="d0c68-131">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="d0c68-132">Viene illustrato come usare le classi `ConnectionStringBuilder` per creare stringhe di connessione valide in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0c68-132">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="d0c68-133">[Stringhe di connessione e file di configurazione](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="d0c68-133">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="d0c68-134">Viene illustrato come archiviare e recuperare le stringhe di connessione nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0c68-134">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="d0c68-135">[Sintassi delle stringhe di connessione](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="d0c68-135">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="d0c68-136">Viene descritto come configurare stringhe di connessione specifiche del provider per `SqlClient`, `OracleClient`, `OleDb` e `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="d0c68-136">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="d0c68-137">[Protezione delle informazioni di connessione](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="d0c68-137">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="d0c68-138">Vengono illustrate tecniche per proteggere le informazioni usate per la connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0c68-138">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0c68-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0c68-139">See also</span></span>

- [<span data-ttu-id="d0c68-140">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="d0c68-140">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="d0c68-141">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d0c68-141">ADO.NET Overview</span></span>](ado-net-overview.md)
