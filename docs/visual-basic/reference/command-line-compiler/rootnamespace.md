---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005205"
---
# <a name="-rootnamespace"></a>-rootnamespace
Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`namespace`|Nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.|  
  
## <a name="remarks"></a>Osservazioni  
 Se si utilizza il file eseguibile di Visual Studio (devenv. exe) per compilare un progetto creato in Visual Studio Integrated Development Environment, `-rootnamespace` utilizzare per specificare il valore della <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà. Per ulteriori informazioni, vedere [Opzioni della riga di comando devenv](/visualstudio/ide/reference/devenv-command-line-switches) .  
  
 Usare il disassembler MSIL di Common Language Runtime`Ildasm.exe`() per visualizzare i nomi degli spazi dei nomi nel file di output.  
  
|Per impostare-RootNamespace in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **applicazione** .<br />3. modificare il valore nella casella **spazio dei nomi radice** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e racchiude tutte le dichiarazioni di tipo nello spazio dei nomi. `mynamespace`  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Ildasm. exe (disassembler IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
