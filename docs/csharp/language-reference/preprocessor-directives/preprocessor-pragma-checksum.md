---
title: '#pragma checksum - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 36e5602f0a0b872a4aa6cdac64b49b1d1c708795
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877517"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (Riferimenti per C#)
Genera i checksum per i file di origine per favorire il debug delle pagine ASP.NET.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a>Parametri  
 `"filename"`  
 Nome del file che richiede il monitoraggio per modifiche o aggiornamenti.  
  
 `"{guid}"`  
 Identificatore univoco globale (GUID, Globally Unique Identifier) dell'algoritmo hash.  
  
 `"checksum_bytes"`  
 Stringa di cifre esadecimali che rappresenta i byte del checksum. Deve essere un numero pari di cifre esadecimali. Un numero dispari di cifre genera un avviso in fase di compilazione, pertanto la direttiva viene ignorata.  
  
## <a name="remarks"></a>Osservazioni  
 Il debugger di Visual Studio usa un checksum per trovare sempre l'origine corretta. Il compilatore calcola il checksum di un file di origine, quindi genera l'output nel file del database di programma (PDB). Il PDB viene quindi usato dal debugger per eseguire il confronto con il checksum calcolato per il file di origine.  
  
 Questa soluzione non funziona per i progetti ASP.NET, perché il checksum calcolato fa riferimento al file di origine generato anziché al file con estensione aspx. Per risolvere questo problema, `#pragma checksum` offre il supporto del checksum per le pagine ASP.NET.  
  
 Quando si crea un progetto ASP.NET in Visual C# il file di origine generato contiene un checksum per il file con estensione aspx, dal quale viene generata l'origine. Queste informazioni vengono quindi scritte dal compilatore nel file PDB.  
  
 Se il compilatore non rileva alcuna direttiva `#pragma checksum` nel file, calcola il checksum e scrive il valore nel file PDB.  
  
## <a name="example"></a>Esempio  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)
