---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 5892baaa2732d95cfe698147e06b914af968adc5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929418"
---
# <a name="-keycontainer"></a>-keycontainer
Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`container`|Richiesto. File contenitore contenente la chiave. Racchiudere il nome file tra virgolette ("") se il nome contiene uno spazio.|  
  
## <a name="remarks"></a>Note  
 Il compilatore crea il componente condivisibile inserendo una chiave pubblica nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata. Per generare un file di chiave, digitare `sn -k file` nella riga di comando. L' `-i` opzione installa la coppia di chiavi in un contenitore. Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Se si esegue la `-target:module`compilazione con, il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).  
  
 È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.  
  
 Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) .  
  
> [!NOTE]
> L' `-keycontainer` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila il file `Input.vb` di origine e specifica un contenitore di chiavi.  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](../../../standard/assembly/index.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
