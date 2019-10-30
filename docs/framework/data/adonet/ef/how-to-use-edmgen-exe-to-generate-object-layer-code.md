---
title: 'Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 9182f815a502488f955f64f6c19aad7865d0c7c6
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039989"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti
In questo argomento viene illustrato come utilizzare lo strumento [Generatore EDM (EdmGen. exe)](edm-generator-edmgen-exe.md) per generare il codice del livello oggetti in base al file con estensione csdl.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Per generare il codice del livello oggetti per il modello School per un progetto di Visual Basic usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [la pagina relativa alla creazione del database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School o ottenere il file School.csdl. Per altre informazioni, vedere [procedura: usare EdmGen. exe per generare i file di modello e di mapping](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Per generare il codice del livello oggetti per il modello School per un progetto di C# usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [la pagina relativa alla creazione del database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School o ottenere il file School.csdl. Per altre informazioni, vedere [procedura: usare EdmGen. exe per generare i file di modello e di mapping](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](modeling-and-mapping.md)
- [Procedura: configurare manualmente un progetto di Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: pre-generare viste per migliorare le prestazioni delle query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Procedura: Usare EdmGen.exe per generare i file di modello e di mapping](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
