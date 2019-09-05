---
title: 'Procedura: Usare EdmGen.exe per convalidare file di modello e di mapping'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 4495ff3c5d55779e9db113a2a59361b643841382
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251384"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Procedura: Usare EdmGen.exe per convalidare file di modello e di mapping
In questo argomento viene illustrato come utilizzare lo strumento [Generatore EDM (EdmGen. exe)](edm-generator-edmgen-exe.md) per convalidare i file di modello e di mapping. Per ulteriori informazioni, vedere [Entity Data Model](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Per convalidare il modello School usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [la pagina relativa alla creazione del database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School. Per altre informazioni, vedere [Procedura: Utilizzare EdmGen. exe per generare i file](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping.  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Configurare manualmente un progetto di Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: Pre-genera viste per migliorare le prestazioni delle query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Procedura: Usare EdmGen. exe per generare il codice del livello oggetti](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
