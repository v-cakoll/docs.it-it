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
ms.openlocfilehash: b6a2f3ba0772d8f8c8c6a762a1be01703d21b778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403135"
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
  
## <a name="remarks"></a>Commenti  
 Se si utilizza il file eseguibile di Visual Studio (devenv. exe) per compilare un progetto creato in Visual Studio Integrated Development Environment, utilizzare `-rootnamespace` per specificare il valore della <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Proprietà. Per ulteriori informazioni, vedere [Opzioni della riga di comando devenv](/visualstudio/ide/reference/devenv-command-line-switches) .  
  
 Usare il disassembler MSIL di Common Language Runtime ( `Ildasm.exe` ) per visualizzare i nomi degli spazi dei nomi nel file di output.  
  
|Per impostare-RootNamespace in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **applicazione** .<br />3. modificare il valore nella casella **spazio dei nomi radice** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e racchiude tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace` .  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Ildasm. exe (disassembler IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
