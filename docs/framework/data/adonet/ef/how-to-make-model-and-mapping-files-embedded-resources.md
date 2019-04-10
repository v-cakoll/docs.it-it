---
title: 'Procedura: Definire i file di modello e di mapping come risorse incorporate'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: eae3681664ab1fd095487a7b7ed395302faf2588
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329531"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Procedura: Definire i file di modello e di mapping come risorse incorporate
Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] consente di distribuire file di modello e il mapping come risorse incorporate di un'applicazione. L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità. Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione). Gli strumenti [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incorporano i file di modello e di mapping per impostazione predefinita. Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme all'applicazione [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.  
  
### <a name="to-embed-model-and-mapping-files"></a>Per incorporare i file di modello e di mapping  
  
1. Nelle **Esplora soluzioni**, selezionare il file concettuale (CSDL).  
  
2. Nel **delle proprietà** riquadro, impostare **azione di compilazione** al **risorsa incorporata**.  
  
3. Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).  
  
4. In **Esplora soluzioni**, fare doppio clic sul file app. config e quindi modificare il `Metadata` parametri nel `connectionString` attributo basato su uno dei formati seguenti:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione).  
  
## <a name="example"></a>Esempio  
 La stringa di connessione seguente fa riferimento a modello incorporato e file di mapping per il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Questa stringa di connessione è archiviata nel file App.config del progetto.  

## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Procedura: Definire la stringa di connessione](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [Procedura: Compilare una stringa di connessione EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
