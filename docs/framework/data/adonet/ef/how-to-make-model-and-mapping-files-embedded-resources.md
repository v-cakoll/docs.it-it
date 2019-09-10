---
title: 'Procedura: Definire i file di modello e di mapping come risorse incorporate'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 371f8f0317295ee39d543b5637afb93102036b62
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854586"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Procedura: Definire i file di modello e di mapping come risorse incorporate
Il Entity Framework consente di distribuire i file di modello e di mapping come risorse incorporate di un'applicazione. L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità. Per altre informazioni, vedere [Connection Strings](connection-strings.md) (Stringhe di connessione). Per impostazione predefinita, gli strumenti di Entity Data Model incorporano i file di modello e di mapping. Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme a un'applicazione Entity Framework.  
  
> [!NOTE]
> Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.  
  
### <a name="to-embed-model-and-mapping-files"></a>Per incorporare i file di modello e di mapping  
  
1. In **Esplora soluzioni**selezionare il file concettuale (con estensione CSDL).  
  
2. Nel riquadro **Proprietà** impostare azione di **compilazione** su **risorsa incorporata**.  
  
3. Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).  
  
4. In **Esplora soluzioni**fare doppio clic sul file app. config e quindi modificare il `Metadata` parametro nell' `connectionString` attributo in base a uno dei formati seguenti:  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Per altre informazioni, vedere [Connection Strings](connection-strings.md) (Stringhe di connessione).  
  
## <a name="example"></a>Esempio  
 La stringa di connessione seguente fa riferimento ai file di modello e di mapping incorporati per il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Questa stringa di connessione è archiviata nel file App.config del progetto.  

## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](modeling-and-mapping.md)
- [Procedura: Definire la stringa di connessione](how-to-define-the-connection-string.md)
- [Procedura: Compilare una stringa di connessione EntityConnection](how-to-build-an-entityconnection-connection-string.md)
- [Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
