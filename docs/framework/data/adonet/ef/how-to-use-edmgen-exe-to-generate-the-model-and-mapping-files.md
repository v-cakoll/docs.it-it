---
title: 'Procedura: Usare EdmGen.exe per generare i file di modello e di mapping'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: f5781b49817054923cbbbf4d52205b9280ea131a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64632214"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Procedura: Usare EdmGen.exe per generare i file di modello e di mapping
In questo argomento viene illustrato come usare lo strumento Generatore EDM (EdmGen.exe) per generare i seguenti file in base al database School:  
  
- Modello concettuale (file con estensione csdl).  
  
- Modello di archiviazione (file con estensione ssdl).  
  
- Mapping tra i modelli concettuali e di archiviazione (file con estensione msl).  
  
- Codice del livello oggetti in Visual Basic o C#.  
  
- File di visualizzazione.  
  
 Lo strumento EdmGen.exe usa /mode:FullGeneration per la generazione dei file elencati in precedenza. Per altre informazioni sui comandi EdmGen.exe, vedere [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Se si usa EdmGen.exe per generare il modello e i file di mapping, è comunque necessario configurare il progetto di Visual Studio per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
>  Un modello concettuale generato da EdmGen.exe include tutti gli oggetti del database. Per generare un modello concettuale che include solo oggetti specifici, usare la Procedura guidata Entity Data Model. Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Per generare il modello School per un progetto Visual Basic usando EdmGen.exe  
  
1. Creare il database School. Per altre informazioni, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Per generare il modello School per un progetto C# usando EdmGen.exe  
  
1. Creare il database School. Per altre informazioni, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Procedura: Pre-generare viste per migliorare le prestazioni delle Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: Utilizzare EdmGen.exe per convalidare i file di modello e Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
