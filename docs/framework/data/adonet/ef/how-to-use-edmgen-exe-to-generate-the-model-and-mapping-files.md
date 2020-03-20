---
title: 'Procedura: utilizzare EdmGen.exe per generare i file di modello e di mapping'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: ee8297c0833378b2b44800355b47db9caa2dc7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150513"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Procedura: utilizzare EdmGen.exe per generare i file di modello e di mapping
In questo argomento viene illustrato come usare lo strumento Generatore EDM (EdmGen.exe) per generare i seguenti file in base al database School:  
  
- Modello concettuale (file con estensione csdl).  
  
- Modello di archiviazione (file con estensione ssdl).  
  
- Mapping tra i modelli concettuali e di archiviazione (file con estensione msl).  
  
- Codice del livello oggetti in Visual Basic o C#.  
  
- File di visualizzazione.  
  
 Lo strumento EdmGen.exe usa /mode:FullGeneration per la generazione dei file elencati in precedenza. Per ulteriori informazioni sui comandi EdmGen.exe, vedere [Generatore EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Se si utilizza EdmGen.exe per generare il modello e i file di mapping, è comunque necessario configurare il progetto di Visual Studio per l'utilizzo di Entity Framework. Per ulteriori informazioni, vedere [Procedura: configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Un modello concettuale generato da EdmGen.exe include tutti gli oggetti del database. Per generare un modello concettuale che include solo oggetti specifici, usare la Procedura guidata Entity Data Model. Per ulteriori informazioni, vedere [Procedura: utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Per generare il modello School per un progetto Visual Basic usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [Creazione del database di esempio della scuola](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Per generare il modello School per un progetto C# usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [Creazione del database di esempio della scuola](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](modeling-and-mapping.md)
- [Procedura: configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Procedura: pre-generare viste per migliorare le prestazioni di query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET gli strumenti di Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
