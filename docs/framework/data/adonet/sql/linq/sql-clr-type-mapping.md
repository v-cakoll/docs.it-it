---
title: Mapping del tipo SQL-CLR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 885c87439ebf7393380c7ff20165d8587f1b26f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sql-clr-type-mapping"></a>Mapping del tipo SQL-CLR
In LINQ to SQL viene eseguito il mapping del modello di dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione desiderato. Quando viene eseguita l'applicazione, LINQ to SQL converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione. Quando il database restituisce i risultati, questi vengono nuovamente convertiti da LINQ to SQL in oggetti che è possibile usare nel linguaggio di programmazione desiderato.  
  
 Per convertire dati tra il modello a oggetti e il database, un *mapping dei tipi* deve essere definita. LINQ to SQL usa un mapping dei tipi per associare ogni tipo Common Language Runtime (CLR) a un tipo di SQL Server specifico. È possibile definire mapping dei tipi e altre informazioni sul mapping, ad esempio la struttura del database e le relazioni tra tabelle, nel modello a oggetti con mapping basato sugli attributi. In alternativa, è possibile specificare le informazioni sul mapping al di fuori del modello a oggetti con un file di mapping esterno. Per ulteriori informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) e [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 In questo argomento vengono trattati gli aspetti seguenti:  
  
-   [Mapping dei tipi predefiniti](#DefaultTypeMapping)  
  
-   [Tipo di matrice del comportamento in fase di esecuzione del Mapping](#BehaviorMatrix)  
  
-   [Differenze di comportamento tra CLR e l'esecuzione di SQL](#BehaviorDiffs)  
  
-   [Mapping dei tipi enum](#EnumMapping)  
  
-   [Mapping dei tipi numerici](#NumericMapping)  
  
-   [Testo e Mapping XML](#TextMapping)  
  
-   [Data e ora di Mapping](#DateMapping)  
  
-   [Mapping dei tipi binari](#BinaryMapping)  
  
-   [Mapping di tipi vari](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>   
## <a name="default-type-mapping"></a>Mapping dei tipi predefiniti  
 È possibile creare automaticamente il modello a oggetti o il file di mapping esterno tramite Progettazione relazionale oggetti o lo strumento da riga di comando SQLMetal. I mapping dei tipi predefiniti per questi strumenti definiscono i tipi CLR scelti per il mapping alle colonne nel database di SQL Server. Per ulteriori informazioni sull'utilizzo di questi strumenti, vedere [la creazione del modello oggetto](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md).  
  
 È inoltre possibile usare il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A> per creare un database di SQL Server basato sulle informazioni sul mapping nel modello a oggetti o nel file di mapping esterno. I mapping dei tipi predefiniti per il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A> definiscono il tipo di colonne di SQL Server create per eseguire il mapping ai tipi CLR nel modello a oggetti. Per ulteriori informazioni, vedere [procedura: creazione di un Database in modo dinamico](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>   
## <a name="type-mapping-run-time-behavior-matrix"></a>Matrice del comportamento in fase di esecuzione del mapping dei tipi  
 Nel diagramma seguente viene illustrato il comportamento previsto in fase di esecuzione dei mapping dei tipi specifici quando i dati vengono recuperati dal o salvati nel database. Ad eccezione della serializzazione, LINQ to SQL non supporta il mapping tra i tipi di dati CLR o SQL Server non specificati in questa matrice. Per ulteriori informazioni sul supporto della serializzazione, vedere [serializzazione binaria](#BinarySerialization).  
  
> [!NOTE]
>  Alcuni mapping dei tipi possono comportare eccezioni di overflow o di perdita di dati durante la conversione da o verso il database.  
  
### <a name="custom-type-mapping"></a>Mapping dei tipi personalizzato  
 LINQ to SQL consente di usare altri mapping rispetto ai mapping dei tipi predefiniti usati in Progettazione relazionale oggetti, in SQLMetal e dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. È possibile creare mapping dei tipi personalizzati specificandoli in modo esplicito in un file DBML. È quindi possibile usare tale file DBML per creare il file di mapping e di codice del modello a oggetti. Per ulteriori informazioni, vedere [mapping del tipo personalizzato SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>   
## <a name="behavior-differences-between-clr-and-sql-execution"></a>Differenze di comportamento tra l'esecuzione CLR e l'esecuzione SQL  
 A causa di alcune differenze di precisione ed esecuzione tra CLR e SQL Server, è possibile ottenere risultati diversi o riscontrare un comportamento diverso a seconda della posizione in cui vengono eseguiti i calcoli. I calcoli effettuati in query LINQ to SQL vengono effettivamente convertiti in Transact-SQL e quindi eseguiti nel database di SQL Server. I calcoli effettuati al di fuori di query LINQ to SQL vengono eseguiti nel contesto di CLR.  
  
 Di seguito vengono illustrate alcune differenze di comportamento tra CLR e SQL Server:  
  
-   In SQL Server alcuni tipi di dati vengono ordinati in modo diverso rispetto a dati del tipo equivalente in CLR. I dati di SQL Server di tipo `UNIQUEIDENTIFIER`, ad esempio, vengono ordinati in modo diverso dai dati CLR di tipo <xref:System.Guid?displayProperty=nameWithType>.  
  
-   In SQL Server alcune operazioni di confronto tra stringhe vengono gestite in modo diverso rispetto a CLR. In SQL Server il comportamento del confronto tra stringhe dipende dalle impostazioni delle regole di confronto configurate nel server. Per ulteriori informazioni, vedere [utilizzano le regole di confronto](http://go.microsoft.com/fwlink/?LinkId=115330) nella documentazione Online di Microsoft SQL Server.  
  
-   SQL Server può restituire valori diversi per alcune funzioni mappate rispetto ai valori restituiti da CLR. Differiscono, ad esempio, le funzioni di uguaglianza, in quanto SQL Server considera uguali due stringhe solo se differiscono nello spazio vuoto iniziale, mentre tali stringhe vengono considerate diverse in CLR.  
  
<a name="EnumMapping"></a>   
## <a name="enum-mapping"></a>Mapping dei tipi Enum  
 LINQ to SQL supporta il mapping del tipo <xref:System.Enum?displayProperty=nameWithType> CLR ai tipi di SQL Server tramite due modalità diverse:  
  
-   Mapping ai tipi numerici SQL (`TINYINT`, `SMALLINT`, `INT`, `BIGINT`)  
  
     Quando si esegue il mapping di un tipo <xref:System.Enum?displayProperty=nameWithType> CLR a un tipo numerico SQL, viene eseguito il mapping del valore intero sottostante del tipo <xref:System.Enum?displayProperty=nameWithType> CLR al valore della colonna del database di SQL Server. Se, ad esempio, un tipo <xref:System.Enum?displayProperty=nameWithType> denominato `DaysOfWeek` contiene un membro denominato `Tue` con un valore intero sottostante pari a 3, tale membro verrà mappato a un valore del database pari a 3.  
  
-   Mapping ai tipi di testo SQL (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`)  
  
     Quando si esegue il mapping di un tipo <xref:System.Enum?displayProperty=nameWithType> CLR a un tipo di testo SQL, il valore del database SQL viene mappato ai nomi dei membri <xref:System.Enum?displayProperty=nameWithType> CLR. Se, ad esempio, un tipo <xref:System.Enum?displayProperty=nameWithType> denominato `DaysOfWeek` contiene un membro denominato `Tue` con un valore intero sottostante pari a 3, tale membro verrà mappato a un valore del database pari a `Tue`.  
  
> [!NOTE]
>  Quando si esegue il mapping dei tipi di testo SQL a un tipo <xref:System.Enum?displayProperty=nameWithType> CLR, includere solo i nomi dei membri <xref:System.Enum> nella colonna SQL mappata. Gli altri valori non sono supportati nella colonna SQL mappata a <xref:System.Enum>.  
  
 Progettazione relazionale oggetti e lo strumento da riga di comando SQLMetal non consentono di eseguire automaticamente il mapping di un tipo SQL a una classe <xref:System.Enum> CLR. È necessario configurare in modo esplicito questo mapping personalizzando un file DBML per l'uso da parte di Progettazione relazionale oggetti e SQLMetal. Per ulteriori informazioni sui mapping dei tipi personalizzato, vedere [mapping del tipo personalizzato SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
 Poiché una colonna SQL per l'enumerazione è dello stesso tipo di altre colonne numeriche e di testo, Questi strumenti non riconosce la finalità e per impostazione predefinita per il mapping come descritto di seguito [mapping dei tipi numerici](#NumericMapping) e [testo e Mapping XML](#TextMapping) sezioni. Per ulteriori informazioni sulla generazione di codice con il file DBML, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
 Il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> crea una colonna SQL di tipo numerico per eseguire il mapping di un tipo <xref:System.Enum?displayProperty=nameWithType> CLR.  
  
<a name="NumericMapping"></a>   
## <a name="numeric-mapping"></a>Mapping dei tipi numerici  
 LINQ to SQL consente di eseguire il mapping di molti dei tipi numerici CLR e di SQL Server. La tabella seguente illustra i tipi CLR selezionati da Progettazione relazionale oggetti e da SQLMetal durante la compilazione di un modello a oggetti o del file di mapping esterno basato sul database.  
  
|Tipo di SQL Server|Mapping dei tipi CLR predefinito usato in Progettazione relazionale oggetti e SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 La tabella seguente illustra i mapping dei tipi predefiniti usati dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> per determinare il tipo delle colonne SQL create per il mapping ai tipi CLR definiti nel modello a oggetti o nel file di mapping esterno.  
  
|Tipo CLR|Tipo di SQL Server predefinito usato da <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 Benché sia possibile scegliere tra molti altri mapping dei tipi numerici, alcuni possono comportare eccezioni di overflow o di perdita di dati durante la conversione da o verso il database. Per ulteriori informazioni, vedere il [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix).  
  
### <a name="decimal-and-money-types"></a>Tipi Decimal e Money  
 La precisione predefinita di SQL Server `DECIMAL` tipo (18 cifre decimali a sinistra e a destra del separatore decimale) è molto inferiore alla precisione di CLR <!--zz <xref:System.Decima?displayProperty=nameWithType>l --> `Decimal` tipo di cui è abbinato per impostazione predefinita. Questa differenza può comportare una perdita di precisione quando si salvano dati nel database. Può tuttavia verificarsi il contrario se il tipo `DECIMAL` di SQL Server viene configurato con più di 29 cifre di precisione. Quando un tipo `DECIMAL` di SQL Server viene configurato con una precisione maggiore del tipo <xref:System.Decimal?displayProperty=nameWithType> CLR, può verificarsi una perdita di precisione durante il recupero di dati dal database.  
  
 I tipi `MONEY` e `SMALLMONEY` di SQL Server, abbinati anch'essi al tipo <xref:System.Decimal?displayProperty=nameWithType> CLR per impostazione predefinita, hanno una precisione di gran lunga inferiore, che può comportare eccezioni di overflow o di perdita di dati quando si salvano dati nel database.  
  
<a name="TextMapping"></a>   
## <a name="text-and-xml-mapping"></a>Mapping dei tipi di testo e XML  
 LINQ to SQL consente di eseguire il mapping anche di molti tipi XML e basati su testo. La tabella seguente illustra i tipi CLR selezionati da Progettazione relazionale oggetti e da SQLMetal durante la compilazione di un modello a oggetti o del file di mapping esterno basato sul database.  
  
|Tipo di SQL Server|Mapping dei tipi CLR predefinito usato in Progettazione relazionale oggetti e SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 La tabella seguente illustra i mapping dei tipi predefiniti usati dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> per determinare il tipo delle colonne SQL create per il mapping ai tipi CLR definiti nel modello a oggetti o nel file di mapping esterno.  
  
|Tipo CLR|Tipo di SQL Server predefinito usato da <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=nameWithType>[]|`NVARCHAR(4000)`|  
|Tipo personalizzato che implementa `Parse()` e `ToString()`|`NVARCHAR(MAX)`|  
  
 Benché sia possibile scegliere tra molti altri mapping dei tipi XML e basati su testo, alcuni possono comportare eccezioni di overflow o di perdita di dati durante la conversione da o verso il database. Per ulteriori informazioni, vedere il [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix).  
  
### <a name="xml-types"></a>Tipi XML  
 Il tipo di dati `XML` di SQL Server è disponibile a partire da Microsoft SQL Server 2005. È possibile eseguire il mapping del tipo di dati `XML` di SQL Server a <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> o <xref:System.String>. Se nella colonna sono archiviati frammenti XML che non possono essere letti in <xref:System.Xml.Linq.XElement>, per evitare errori di runtime è necessario eseguire il mapping della colonna a <xref:System.String>. Di seguito vengono indicati i frammenti XML di cui è necessario eseguire il mapping a <xref:System.String>:  
  
-   Una sequenza di elementi XML  
  
-   Attributi  
  
-   Identificatori pubblici  
  
-   Commenti  
  
 Anche se è possibile eseguire il mapping <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> a SQL Server, come illustrato nel [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix), <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> non dispone di alcun mapping dei tipi SQL Server predefinito per questi tipi.  
  
### <a name="custom-types"></a>Tipi personalizzati  
 Se una classe implementa `Parse()` e `ToString()`, è possibile eseguire il mapping dell'oggetto a qualsiasi tipo di testo SQL (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`, `TEXT`, `NTEXT`, `XML`). L'oggetto viene archiviato nel database inviando il valore restituito da `ToString()` alla colonna mappata del database. L'oggetto viene ricostruito richiamando `Parse()` sulla stringa restituita dal database.  
  
> [!NOTE]
>  LINQ to SQL non supporta la serializzazione tramite <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>.  
  
<a name="DateMapping"></a>   
## <a name="date-and-time-mapping"></a>Mapping dei tipi data e ora  
 LINQ to SQL consente di eseguire il mapping di molti dei tipi data e ora di SQL Server. La tabella seguente illustra i tipi CLR selezionati da Progettazione relazionale oggetti e da SQLMetal durante la compilazione di un modello a oggetti o del file di mapping esterno basato sul database.  
  
|Tipo di SQL Server|Mapping dei tipi CLR predefinito usato in Progettazione relazionale oggetti e SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 La tabella seguente illustra i mapping dei tipi predefiniti usati dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> per determinare il tipo delle colonne SQL create per il mapping ai tipi CLR definiti nel modello a oggetti o nel file di mapping esterno.  
  
|Tipo CLR|Tipo di SQL Server predefinito usato da <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 Benché sia possibile scegliere tra molti altri mapping dei tipi data e ora, alcuni possono comportare eccezioni di overflow o di perdita di dati durante la conversione da o verso il database. Per ulteriori informazioni, vedere il [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix).  
  
> [!NOTE]
>  I tipi di dati `DATETIME2`, `DATETIMEOFFSET`, `DATE` e `TIME` di SQL Server sono disponibili a partire da Microsoft SQL Server 2008. LINQ to SQL supporta il mapping a questi nuovi tipi a partire da .NET Framework versione 3.5 SP1.  
  
### <a name="systemdatetime"></a>System.Datetime  
 L'intervallo e la precisione del tipo <xref:System.DateTime?displayProperty=nameWithType> CLR sono maggiori dell'intervallo e della precisione del tipo `DATETIME` di SQL Server, che rappresenta il mapping dei tipi predefiniti per il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>. Per evitare eccezioni relative a date non incluse nell'intervallo di `DATETIME`, usare `DATETIME2`, disponibile a partire da Microsoft SQL Server 2008. `DATETIME2`può corrispondere all'intervallo e la precisione del tipo <xref:System.DateTime?displayProperty=nameWithType>.  
  
 Le date di SQL Server non includono alcun concetto di <xref:System.TimeZone>, una funzionalità ampiamente supportata in CLR. I valori di <xref:System.TimeZone> vengono salvati così come sono nel database senza conversione <xref:System.TimeZone>, indipendentemente dalle informazioni <xref:System.DateTimeKind> originali. Quando i valori di <xref:System.DateTime> vengono recuperati dal database, il relativo valore viene caricato così com'è in un oggetto <xref:System.DateTime> con un valore <xref:System.DateTimeKind> corrispondente a <xref:System.DateTimeKind.Unspecified>. Per ulteriori informazioni su supportato <xref:System.DateTime?displayProperty=nameWithType> metodi, vedere [metodi System. DateTime](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md).  
  
### <a name="systemtimespan"></a>System.TimeSpan  
 Microsoft SQL Server 2008 e .NET Framework 3.5 SP1 consentono di eseguire il mapping del tipo <xref:System.TimeSpan?displayProperty=nameWithType> CLR al tipo `TIME` di SQL Server. Vi è tuttavia una notevole differenza tra l'intervallo supportato dal tipo <xref:System.TimeSpan?displayProperty=nameWithType> CLR e quello supportato dal tipo `TIME` di SQL Server. Se si esegue il mapping di valori minori di 0 o maggiori delle ore 23.59.59.9999999 al tipo `TIME` di SQL Server, verranno restituite eccezioni di overflow. Per ulteriori informazioni, vedere [metodi System. TimeSpan](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md).  
  
 In Microsoft SQL Server 2000 e SQL Server 2005 non è possibile eseguire il mapping dei campi del database a <xref:System.TimeSpan>. Sono tuttavia supportate operazioni su <xref:System.TimeSpan>, in quanto è possibile che i valori <xref:System.TimeSpan> vengano restituiti da una sottrazione <xref:System.DateTime> o vengano introdotti in un'espressione come un valore letterale o una variabile associata.  
  
<a name="BinaryMapping"></a>   
## <a name="binary-mapping"></a>Mapping dei tipi binari  
 Vi sono molti tipi di SQL Server di cui è possibile eseguire il mapping al tipo <xref:System.Data.Linq.Binary?displayProperty=nameWithType> CLR. La tabella seguente illustra i tipi di SQL Server che determinano in Progettazione relazionale oggetti e SQLMetal la definizione di un tipo <xref:System.Data.Linq.Binary?displayProperty=nameWithType> CLR durante la compilazione di un modello a oggetti o un file di mapping esterno basato sul database.  
  
|Tipo di SQL Server|Mapping dei tipi CLR predefinito usato in Progettazione relazionale oggetti e SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`con il `FILESTREAM` attributo|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 La tabella seguente illustra i mapping dei tipi predefiniti usati dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> per determinare il tipo delle colonne SQL create per il mapping ai tipi CLR definiti nel modello a oggetti o nel file di mapping esterno.  
  
|Tipo CLR|Tipo di SQL Server predefinito usato da <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 Benché sia possibile scegliere tra molti altri mapping dei tipi binari, alcuni possono comportare eccezioni di overflow o di perdita di dati durante la conversione da o verso il database. Per ulteriori informazioni, vedere il [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix).  
  
### <a name="sql-server-filestream"></a>FILESTREAM di SQL Server  
 L'attributo `FILESTREAM` per colonne `VARBINARY(MAX)` è disponibile a partire da Microsoft SQL Server 2008 e può essere mappato con LINQ to SQL a partire da .NET Framework versione 3.5 SP1.  
  
 Benché sia possibile eseguire il mapping di colonne `VARBINARY(MAX)` con l'attributo `FILESTREAM` a oggetti <xref:System.Data.Linq.Binary>, il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> non è in grado di creare automaticamente colonne con l'attributo `FILESTREAM`. Per ulteriori informazioni su `FILESTREAM`, vedere [Panoramica di FILESTREAM](http://go.microsoft.com/fwlink/?LinkId=115291) nella documentazione Online di Microsoft SQL Server.  
  
<a name="BinarySerialization"></a>   
### <a name="binary-serialization"></a>Serializzazione binaria  
 Se una classe implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>, è possibile serializzare un oggetto in qualsiasi campo binario SQL, ad esempio `BINARY`, `VARBINARY` o `IMAGE`. L'oggetto viene serializzato e deserializzato in base alla modalità di implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable>. Per ulteriori informazioni, vedere [serializzazione binaria](http://go.microsoft.com/fwlink/?LinkId=115581).  
  
<a name="MiscMapping"></a>   
## <a name="miscellaneous-mapping"></a>Mapping di tipi vari  
 La tabella seguente illustra i mapping dei tipi predefiniti per alcuni tipi vari non inclusi nelle sezioni precedenti. La tabella seguente illustra i tipi CLR selezionati da Progettazione relazionale oggetti e da SQLMetal durante la compilazione di un modello a oggetti o del file di mapping esterno basato sul database.  
  
|Tipo di SQL Server|Mapping dei tipi CLR predefinito usato in Progettazione relazionale oggetti e SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 La tabella seguente illustra i mapping dei tipi predefiniti usati dal metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> per determinare il tipo delle colonne SQL create per il mapping ai tipi CLR definiti nel modello a oggetti o nel file di mapping esterno.  
  
|Tipo CLR|Tipo di SQL Server predefinito usato da <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 LINQ to SQL non supporta altri mapping per tali tipi vari.  Per ulteriori informazioni, vedere il [tipo Mapping matrice fase di esecuzione comportamento](#BehaviorMatrix).  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)  
 [Funzioni e tipi di dati](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [Mancata corrispondenza di tipo SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)
