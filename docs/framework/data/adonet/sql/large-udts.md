---
title: Tipi definiti dall'utente di grandi dimensioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: f55f6eccf3566a2391204e1ca4349ae5dff01954
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148556"
---
# <a name="large-udts"></a>Tipi definiti dall'utente di grandi dimensioni
I tipi definiti dall'utente (UDT) consentono agli sviluppatori di estendere il sistema di tipi scalare del server archiviando oggetti Common Language Runtime (CLR) in un database di SQL Server. I tipi definiti dall'utente possono contenere più elementi e avere comportamenti che, a differenza dei tradizionali tipi di dati alias, sono costituiti da un solo tipo di dati di sistema di SQL Server.  
  
> [!NOTE]
> Per sfruttare il supporto SqlClient migliorato per i tipi UDT di grandi dimensioni, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).  
  
 In precedenza, i tipi definiti dall'utente erano limitati a una dimensione massima di 8 kilobyte. In SQL Server 2008 questa limitazione è stata rimossa per i tipi definiti dall'utente con il formato <xref:Microsoft.SqlServer.Server.Format.UserDefined>.  
  
 Per informazioni complete sui tipi definiti dall'utente, vedere la documentazione online di SQL Server relativa alla versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
1. [Tipi definiti dall'utente per CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Recupero di schemi UDT tramite GetSchema  
 Il metodo <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> di <xref:System.Data.SqlClient.SqlConnection> restituisce le informazioni sullo schema del database in un <xref:System.Data.DataTable>. Per ulteriori informazioni, vedere [Raccolte di schemi di SQL Server.](../sql-server-schema-collections.md)  
  
### <a name="getschematable-column-values-for-udts"></a>Valori della colonna GetSchemaTable per i tipi UDT  
 Il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> di un <xref:System.Data.SqlClient.SqlDataReader> restituisce un <xref:System.Data.DataTable> che descrive i metadati della colonna. Nella tabella seguente vengono descritte le differenze tra SQL Server 2005 e SQL Server 2008 riguardo ai metadati delle colonne per i tipi definiti dall'utente di grandi dimensioni.  
  
|Colonna SqlDataReader|SQL Server 2005|SQL Server 2008 e versioni successive|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Variabile|Variabile|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|Istanza UDT|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|Istanza UDT|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Nome in tre parti specificato come *Database.SchemaName.TypeName*.|  
|`IsLong`|Variabile|Variabile|  
  
## <a name="sqldatareader-considerations"></a>Considerazioni su SqlDataReader  
 <xref:System.Data.SqlClient.SqlDataReader> è stato esteso a partire da SQL Server 2008 per supportare il recupero di valori UDT di grandi dimensioni. La modalità di elaborazione dei valori UDT di grandi dimensioni da parte di un <xref:System.Data.SqlClient.SqlDataReader> dipende dalla versione di SQL Server in uso, nonché dall'elemento `Type System Version` specificato nella stringa di connessione. Per altre informazioni, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 I metodi seguenti di <xref:System.Data.SqlClient.SqlDataReader> restituiranno un <xref:System.Data.SqlTypes.SqlBinary> anziché un tipo definito dall'utente quando `Type System Version` è impostato su SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 I metodi seguenti restituiranno una matrice di `Byte[]` anziché un tipo definito dall'utente quando `Type System Version` è impostato su SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Si noti che non viene eseguita alcuna conversione per la versione corrente di ADO.NET.  
  
## <a name="specifying-sqlparameters"></a>Specifica di SqlParameter  
 Le proprietà <xref:System.Data.SqlClient.SqlParameter> seguenti sono state estese per funzionare con i tipi definiti dall'utente di grandi dimensioni.  
  
|Proprietà SqlParameter|Descrizione|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Ottiene o imposta un oggetto che rappresenta il valore del parametro. Il valore predefinito è Null. La proprietà può essere `SqlBinary`, `Byte[]` o un oggetto gestito.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Ottiene o imposta un oggetto che rappresenta il valore del parametro. Il valore predefinito è Null. La proprietà può essere `SqlBinary`, `Byte[]` o un oggetto gestito.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Ottiene o imposta la dimensione del valore del parametro da risolvere. Il valore predefinito è 0. La proprietà può essere un numero intero che rappresenta la dimensione del valore del parametro. Per gli UDT di grandi dimensioni, può trattarsi delle dimensioni effettive dell'UDT oppure di -1 per i tipi sconosciuti.|  
  
## <a name="retrieving-data-example"></a>Esempio di recupero di dati  
 Il frammento di codice seguente illustra come recuperare dati UDT di grandi dimensioni. La variabile `connectionString` presuppone una connessione valida a un database SQL Server e la variabile `commandString` presuppone un'istruzione SELECT valida con la colonna chiave primaria elencata per prima.  
  
```csharp  
using (SqlConnection connection = new SqlConnection(
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione di parametri e tipi di dati dei parametri](../configuring-parameters-and-parameter-data-types.md)
- [Recupero di informazioni sullo schema del database](../retrieving-database-schema-information.md)
- [Mapping dei tipi di dati SQL Server](../sql-server-data-type-mappings.md)
- [SQL Server Binary and Large-Value Data](sql-server-binary-and-large-value-data.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
