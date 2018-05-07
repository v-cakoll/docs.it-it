---
title: -/langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 82a7114027451d1342e6dc0846799933ce44d968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-visual-basic"></a>-/langversion (Visual Basic)
Indica al compilatore di accettare solo la sintassi che è incluso nella versione specificata del linguaggio Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argomenti  
 `version`  
 Obbligatorio. La versione della lingua da utilizzare durante la compilazione. I valori accettati sono `9`, `9.0`, `10`, e `10.0`.  
  
## <a name="remarks"></a>Note  
 Il `-langversion` opzione specifica quale il compilatore accetta di sintassi. Ad esempio, se si specifica che la lingua è 9.0, il compilatore genera errori di sintassi che è valida solo nella versione 10.0 e versioni successive.  
  
 È possibile utilizzare questa opzione quando si sviluppano applicazioni che diverse versioni di .NET Framework. Ad esempio, se la destinazione è .NET Framework 3.5, è possibile utilizzare questa opzione per assicurarsi che non utilizzino la sintassi di linguaggio versione 10.0.  
  
 È possibile impostare `-langversion` direttamente solo tramite la riga di comando. Per altre informazioni, vedere [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `sample.vb` per Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
