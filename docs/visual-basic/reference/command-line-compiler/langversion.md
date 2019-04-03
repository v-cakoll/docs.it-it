---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839722"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Indica al compilatore di accettare solo sintassi inclusa nella versione specificata del linguaggio Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argomenti  
 `version`  
 Obbligatorio. Versione del linguaggio da utilizzare durante la compilazione. Valori accettati sono `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` e `latest`.

 Uno dei numeri interi può anche essere specificato tramite `.0` come la versione secondaria, ad esempio, `11.0`.

 È possibile visualizzare l'elenco di tutti i possibili valori specificando `-langversion:?` nella riga di comando.  
  
## <a name="remarks"></a>Note  
 Il `-langversion` opzione specifica quale sintassi il compilatore accetta. Ad esempio, se si specifica che la versione del linguaggio è 9.0, il compilatore genera errori di sintassi che è valida solo nella versione 10.0 e versioni successive.  
  
 È possibile usare questa opzione quando si sviluppano applicazioni destinati a versioni diverse di .NET Framework. Ad esempio, se si usa .NET Framework 3.5, è possibile utilizzare questa opzione per assicurarsi di non usare la sintassi di linguaggio versione 10.0.  
  
 È possibile impostare `-langversion` direttamente solo tramite la riga di comando. Per altre informazioni, vedere [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `sample.vb` per Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
