---
title: Raccolte di schemi comuni
ms.date: 03/30/2017
ms.assetid: 50127ced-2ac8-4d7a-9cd1-5c98c655ff03
ms.openlocfilehash: b6c2c89101f3304a0cab014de2def22195541471
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249474"
---
# <a name="common-schema-collections"></a>Raccolte di schemi comuni
Le raccolte di schemi comuni sono le raccolte di schemi implementati da ciascun provider gestito .NET Framework. È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle raccolte di schemi supportate chiamando il metodo **GetSchema** senza argomenti o con il nome della raccolta di schemi "MetaDataCollections". In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco delle raccolte di schemi supportati, il numero delle restrizioni supportate da ciascuna raccolta e il numero di parti identificatore usate. Tutte le colonne richieste vengono descritte in queste raccolte. I provider hanno la possibilità di aggiungere colonne, se necessario. Ad esempio, `SqlClient` e `OracleClient` aggiungono ParameterName alla raccolta delle restrizioni.  
  
 Se un provider non è in grado di determinare il valore di una colonna richiesta, verrà restituito null.  
  
 Per ulteriori informazioni sull'utilizzo dei metodi **GetSchema,** vedere [GetSchema e raccolte di schemi](getschema-and-schema-collections.md).  
  
## <a name="metadatacollections"></a>MetaDataCollections  
 In questa raccolta di schemi vengono riportate informazioni su tutte le raccolte di schemi supportate dal provider gestito di .NET Framework attualmente usato per la connessione al database.  
  
|ColumnName|DataType|Descrizione|  
|----------------|--------------|-----------------|  
|CollectionName|string|Nome della raccolta da passare al metodo **GetSchema** per restituire la raccolta.|  
|NumberOfRestrictions|INT|Il numero di restrizioni che è possibile specificare per la raccolta.|  
|NumberOfIdentifierParts|INT|Il numero di parti nel nome dell'oggetto di database/identificatore composito. Ad esempio, in SQL Server 3 corrisponde alle tabelle e 4 alle colonne. In Oracle 2 corrisponde alle tabelle e 3 alle colonne.|  
  
## <a name="datasourceinformation"></a>DataSourceInformation  
 La raccolta di schemi espone informazioni sull'origine dati a cui è connesso il provider gestito .NET Framework.  
  
|ColumnName|DataType|Descrizione|  
|----------------|--------------|-----------------|  
|CompositeIdentifierSeparatorPattern|string|L'espressione regolare che corrisponde ai separatori compositi in un identificatore composito. Ad esempio, "\\". (per SQL Server)\@ \\o "&#124;". (per Oracle).<br /><br /> Un identificatore composito è in genere quello utilizzato per un nome di\@oggetto di database, ad esempio: pubs.dbo.authors o pubs dbo.authors.A composite identifier is typically what is used for a database object name, for example: pubs.dbo.authors or pubs dbo.authors.<br /><br /> Per SQL Server, utilizzare\\l'espressione regolare " .". Per OracleClient,\@ utilizzare \\"&#124;.".<br /><br /> Per ODBC, usare Catalog_name_seperator.<br /><br /> Per OLE DB, usare DBLITERAL_CATALOG_SEPARATOR o DBLITERAL_SCHEMA_SEPARATOR.|  
|DataSourceProductName|string|Il nome del prodotto a cui ha avuto accesso il provider, come "Oracle" o "SQLServer".|  
|DataSourceProductVersion|string|Indica la versione del prodotto a cui ha avuto accesso il provider, nel formato nativo delle origini dati e non in formato Microsoft.<br /><br /> In alcuni casi DataSourceProductVersion e DataSourceProductVersionNormalized corrisponderanno allo stesso valore. Nel caso di OLE DB e ODBC risulteranno sempre uguali poiché sono mappati alla stessa chiamata di funzione nell'API nativo sottostante.|  
|DataSourceProductVersionNormalized|string|Una versione normalizzata per l'origine dati, che è possibile confrontare con `String.Compare()`. Il formato è lo stesso in tutte le versioni del provider per evitare che la versione 10 venga elencata tra la versione 1 e la versione 2.<br /><br /> For example, the Oracle provider uses a format of "nn.nn.nn.nn.nn" for its normalized version, which causes an Oracle 8i data source to return "08.01.07.04.01". SQL Server utilizza il tipico formato Microsoft "nn.nn.nnnn".<br /><br /> In alcuni casi DataSourceProductVersion e DataSourceProductVersionNormalized corrisponderanno allo stesso valore. Nel caso di OLE DB e ODBC risulteranno sempre uguali poiché sono mappati alla stessa chiamata di funzione nell'API nativo sottostante.|  
|GroupByBehavior|<xref:System.Data.Common.GroupByBehavior>|Specifica il rapporto tra le colonne nella clausola GROUP BY e le colonne non aggregate nell'elenco di selezione.|  
|IdentifierPattern|string|Un'espressione regolare che corrisponde a un identificatore e dispone di un valore di corrispondenza dell'identificatore. Ad esempio "[A-Za-z0-9_#$]".|  
|IdentifierCase|<xref:System.Data.Common.IdentifierCase>|Indica se per gli identificatori non delimitati viene eseguita la distinzione tra maiuscole e minuscole.|  
|OrderByColumnsInSelect|bool|Specifica se le colonne nella clausola ORDER BY devono essere presenti nell'elenco di selezione. Il valore true indica che le colonne devono risultare nell'elenco di selezione, mentre il valore false indica che non è necessario.|  
|ParameterMarkerFormat|string|Una stringa di formato che rappresenta la modalità di formattazione di un parametro.<br /><br /> Se i parametri denominati sono supportati dall'origine dati, il primo segnalibro di questa stringa deve trovarsi nella posizione in cui verrà formattato il nome del parametro.<br /><br /> Ad esempio, se l'origine dati prevede che i parametri siano denominati{0}e preceduti da un ':' questo sarebbe ": ". Quando si esegue la formattazione con il nome di parametro "p1" la stringa risultante sarà ":p1".<br /><br /> Se l'origine dati prevede che i\@parametri siano preceduti dal prefisso '{0}', ma i nomi li\@includono già, questo\@sarebbe ' ' e il risultato della formattazione di un parametro denominato " p1" sarà semplicemente " p1".<br /><br /> Per le origini dati che non prevedono parametri denominati e prevedono l'utilizzo del carattere '?', la stringa di formato può essere specificata semplicemente come '?', che ignorerebbe il nome del parametro. Per OLE DB restituiamo '?'.|  
|ParameterMarkerPattern|string|Un'espressione regolare che corrisponde al marcatore di parametro. Avrà un valore corrispondente per il nome del parametro, se disponibile.<br /><br /> Ad esempio, se i parametri\@denominati sono supportati con un carattere di lead-in\@che verrà incluso nel nome del parametro, sarà: "( [A-z-z0-9_'])".<br /><br /> Tuttavia, se i parametri denominati sono supportati con un ':' come carattere di lead-in e non fa parte del nome\*del parametro, questo sarebbe: ":([A-a-z0-9_'] )".<br /><br /> Naturalmente, se l'origine dati non supporta i parametri denominati, questo sarebbe semplicemente "?".|  
|ParameterNameMaxLength|INT|La lunghezza massima del nome del parametro in caratteri. In Visual Studio si presuppone che se i nomi di parametri sono supportati, il valore minimo per la lunghezza massima corrisponderà a 30 caratteri.<br /><br /> Se l'origine dati non supporta i parametri denominati, questa proprietà restituisce zero.|  
|ParameterNamePattern|string|Un'espressione regolare che corrisponde ai nomi di parametro validi. Origini dati diverse hanno regole diverse per i caratteri che è possibile usare con i nomi di parametro.<br /><br /> In Visual Studio si presuppone che se sono supportati i nomi di parametro, i caratteri "\p{Lu}\p{Ll}\p{Lt}\p{Lm}\p{Lo}\p{Nl}\p{Nd}" rappresentano il set di caratteri minimo supportato, valido per i nomi di parametro.|  
|QuotedIdentifierPattern|string|Un'espressione regolare che corrisponde a un identificatore delimitato e dispone di un valore di corrispondenza dell'identificatore senza virgolette. Ad esempio, se l'origine dati utilizzava virgolette doppie per identificare\\gli identificatori tra virgolette, si tratterebbe di:"(([[ s "]&#124;\\"\\")|  
|QuotedIdentifierCase|<xref:System.Data.Common.IdentifierCase>|Indica se per gli identificatori delimitati viene eseguita la distinzione tra maiuscole e minuscole.|  
|StatementSeparatorPattern|string|Un'espressione regolare che corrisponde al separatore di istruzione.|  
|StringLiteralPattern|string|Un'espressione regolare che corrisponde a una stringa letterale e dispone di un valore di corrispondenza del valore letterale. Ad esempio, se l'origine dati utilizzava virgolette singole per identificare le stringhe, si tratta di: "('(['']&#124;'')"',')"'|  
|SupportedJoinOperators|<xref:System.Data.Common.SupportedJoinOperators>|Specifica i tipi di istruzioni join di SQL supportati dall'origine dati.|  
  
## <a name="datatypes"></a>DataTypes  
 La raccolta di schemi espone informazioni sui tipi di dati supportati dal database al quale è connesso il provider gestito .NET Framework.  
  
|ColumnName|DataType|Descrizione|  
|----------------|--------------|-----------------|  
|TypeName|string|Il nome del tipo di dati specifico del provider.|  
|ProviderDbType|INT|Valore del tipo specifico del provider che deve essere utilizzato quando si specifica il tipo di un parametro. Ad esempio, SqlDbType.Money o OracleType.Blob.|  
|ColumnSize|long|La lunghezza di una colonna o di un parametro non numerico fa riferimento alla lunghezza massima o definita per questo tipo dal provider.<br /><br /> Per i dati di tipo carattere, rappresenta la lunghezza massima o definita in unità, definita dall'origine dati. In Oracle è possibile specificare una lunghezza, quindi la dimensione della memoria effettiva per determinati tipi di dati carattere. Ciò consente di definire solo la lunghezza in unità per Oracle.<br /><br /> Per i tipi di dati data-ora, rappresenta la lunghezza della rappresentazione stringa (se si suppone la massima precisione consentita del componente in frazioni di secondo).<br /><br /> Se il tipo di dati è numerico, rappresenta il limite superiore sulla massima precisione del tipo di dati.|  
|CreateFormat|string|Stringa di formato che indica come aggiungere la colonna a un'istruzione di definizione dei dati, come CREATE TABLE. Ciascun elemento nella matrice CreateParameter deve essere rappresentato da un "marcatore di parametro" nella stringa di formato.<br /><br /> Ad esempio, per il tipo di dati SQL DECIMAL sono necessarie una precisione e una scala. In questo caso, la stringa di{0}{1}formato sarà "DECIMAL( , )".|  
|CreateParameters|string|I parametri di creazione da specificare durante la creazione di una colonna di questo tipo di dati. Ciascun parametro di creazione viene elencato nella stringa, separato da una virgola nell'ordine in cui deve essere fornito.<br /><br /> Ad esempio, per il tipo di dati SQL DECIMAL sono necessarie una precisione e una scala. In questo caso, i parametri di creazione devono contenere la stringa "precision, scale".<br /><br /> In un comando di testo per creare una colonna DECIMAL con una precisione di 10{0}e{1}una scala di 2, il valore della colonna CreateFormat potrebbe essere DECIMAL( , )" e la specifica completa del tipo sarebbe DECIMAL(10,2).|  
|DataType|string|Il nome del tipo di dati .NET Framework.|  
|IsAutoincrementable|bool|true—I valori di questo tipo di dati possono essere a incremento automatico.<br /><br /> false—I valori di questo tipo di dati possono non essere a incremento automatico.<br /><br /> Notare che anche se una colonna di questo tipo di dati può essere a incremento automatico, non significa che tutte le colonne di questo tipo lo siano.|  
|IsBestMatch|bool|true—Il tipo di dati è la corrispondenza più appropriata tra tutti i tipi di dati nell'archivio e il tipo di dati .NET Framework indicato dal valore nella colonna DataType.<br /><br /> false—Il tipo di dati non rappresenta la corrispondenza più appropriata.<br /><br /> Per ciascun set di righe in cui il valore della colonna DataType è lo stesso, la colonna IsBestMatch è impostata su true in una sola riga.|  
|IsCaseSensitive|bool|true—Il tipo di dati è di tipo carattere e viene fatta distinzione tra maiuscole e minuscole.<br /><br /> false—Il tipo di dati è di tipo carattere e viene fatta distinzione tra maiuscole e minuscole.|  
|IsFixedLength|bool|true—Le colonne di questo tipo di dati create dal DDL (Data Definition Language) saranno di lunghezza fissa.<br /><br /> false—Le colonne di questo tipo di dati create dal DDL saranno di lunghezza variabile.<br /><br /> DBNull.Value—Non è noto se il provider eseguirà il mapping del campo con una colonna di lunghezza fissa o di lunghezza variabile.|  
|IsFixedPrecisionScale|bool|true—Il tipo di dati dispone di una precisione e una scala fisse.<br /><br /> false—Il tipo di dati non dispone di una precisione e una scala fisse.|  
|IsLong|bool|true—Il tipo di dati contiene dati molto lunghi. La definizione dei dati molto lunghi è specifica del provider.<br /><br /> false—Il tipo di dati non contiene dati molto lunghi.|  
|IsNullable|bool|true—Il tipo di dati ammette valori null.<br /><br /> false—Il tipo di dati non ammette valori null.<br /><br /> DBNull.Value—Non è noto se il tipo di dati ammette valori null.|  
|IsSearchable|bool|true—Il tipo di dati può essere usato in una clausola WHERE con qualsiasi operatore ad eccezione del predicato LIKE.<br /><br /> false—Il tipo di dati non può essere usato in una clausola WHERE con qualsiasi operatore ad eccezione del predicato LIKE.|  
|IsSearchableWithLike|bool|true—Il tipo di dati può essere usato con il predicato LIKE<br /><br /> false—Il tipo di dati non può essere usato con il predicato LIKE.|  
|IsUnsigned|bool|true—Il tipo di dati è unsigned.<br /><br /> false—Il tipo di dati è signed.<br /><br /> DBNull.Value—Non applicabile al tipo di dati.|  
|MaximumScale|short|Se l'indicatore di tipo è numerico, corrisponde al numero massimo di cifre consentito a destra del separatore decimale. Altrimenti sarà DBNull.Value.|  
|MinimumScale|short|Se l'indicatore di tipo è numerico, corrisponde al numero minimo di cifre consentito a destra del separatore decimale. Altrimenti sarà DBNull.Value.|  
|IsConcurrencyType|bool|true – Il tipo di dati viene aggiornato dal database ogni volta che la riga viene modificata e il valore della colonna è diverso da tutti i valori precedenti<br /><br /> false – Il tipo di dati non viene aggiornato dal database ogni volta che viene modificata la riga<br /><br /> DBNull.Value – il database non supporta questo tipo di dati|  
|IsLiteralSupported|bool|true – Il tipo di dati può essere espresso come valore letterale<br /><br /> false – Il tipo di dati non può essere espresso come valore letterale|  
|LiteralPrefix|string|Il prefisso applicato a un dato valore letterale.|  
|Suffisso letterale|string|Il suffisso applicato a un dato valore letterale.|  
|NativeDataType|string|NativeDataType è una colonna specifica di OLE DB per l'esposizione del tipo di dati OLE DB.|  
  
## <a name="restrictions"></a>Restrizioni  
 La raccolta di schemi espone informazioni sulle restrizioni supportate dal provider gestito .NET Framework usato per la connessione al database.  
  
|ColumnName|DataType|Descrizione|  
|----------------|--------------|-----------------|  
|CollectionName|string|Il nome della raccolta a cui sono applicate queste restrizioni.|  
|RestrictionName|string|Il nome della restrizione nella raccolta.|  
|RestrictionDefault|string|Ignorato.|  
|RestrictionNumber|INT|La posizione effettiva nelle restrizioni delle raccolte in cui rientra questa particolare restrizione.|  
  
## <a name="reservedwords"></a>ReservedWords  
 La raccolta di schemi espone informazioni sulle parole riservate dal database al quale è connesso il provider gestito .NET Framework.  
  
|ColumnName|DataType|Descrizione|  
|----------------|--------------|-----------------|  
|ReservedWord|string|Parola riservata specifica del provider.|  
  
## <a name="see-also"></a>Vedere anche

- [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)
- [Raccolte di schemi e GetSchema](getschema-and-schema-collections.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
