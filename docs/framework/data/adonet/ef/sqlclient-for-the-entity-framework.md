---
title: SqlClient per Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: 430e0e143519f97802c8cef4eee658b482a81880
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425673"
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient per Entity Framework
Contenuto della sezione viene descritto il provider di dati .NET Framework per SQL Server (SqlClient), che consente a Entity Framework di funzionare su Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Attributo Provider dell'elemento Schema  
 `Provider` è un attributo dell'elemento `Schema` in SSDL (Store Schema Definition Language).  
  
 Per usare SqlClient, assegnare la stringa "System.Data.SqlClient" all'attributo `Provider` dell'elemento `Schema`.  
  
## <a name="providermanifesttoken-schema-attribute"></a>Attributo ProviderManifestToken dell'elemento Schema  
 `ProviderManifestToken` è un attributo obbligatorio dell'elemento `Schema` in SSDL. Questo token è usato per caricare il manifesto del provider per gli scenari non in linea. Per altre informazioni sulle `ProviderManifestToken` dell'attributo, vedere [elemento Schema (SSDL)](https://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).  
  
 SqlClient può essere usato come provider di dati per versioni diverse di SQL Server. Queste versioni dispongono di funzionalità diverse. Ad esempio, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] non supporta i tipi `varchar(max)` e `nvarchar(max)` introdotti con [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  
  
 SqlClient produce e accetta i token del manifesto del provider seguenti per versioni diverse di SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  A partire da Visual Studio 2010, il [ADO.NET Entity Data Model Tools](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) non supportano SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Nome dello spazio dei nomi del provider   
 Tutti i provider devono specificare uno spazio dei nomi. Questa proprietà consente a Entity Framework di individuare quale prefisso viene usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Lo spazio dei nomi per i manifesti del provider SqlClient è `SqlServer`. Per altre informazioni sugli spazi dei nomi, vedere [spazi dei nomi](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Tipi  
 Il provider SqlClient per Entity Framework fornisce informazioni di mapping tra i tipi del modello concettuale e i tipi SQL Server. Per altre informazioni, vedere [SqlClient per tipi Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Funzioni  
 Nel provider SqlClient per Entity Framework viene definito l'elenco di funzioni supportate dal provider. Per un elenco delle funzioni supportate, vedere [SqlClient per funzioni Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [SqlClient per funzioni Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [SqlClient per tipi Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Problemi noti in SqlClient per Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Linguaggio Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Riferimenti per il linguaggio](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [Problemi noti di Provider SqlClient per Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
