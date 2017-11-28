---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a>/rootnamespace
Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`namespace`|Il nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.|  
  
## <a name="remarks"></a>Note  
 Se si utilizza il file eseguibile di Visual Studio (Devenv.exe) per compilare un progetto creato nell'ambiente di sviluppo integrato di Visual Studio, usare `/rootnamespace` per specificare il valore di <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà. Vedere [opzioni della riga di comando Devenv](/visualstudio/ide/reference/devenv-command-line-switches) per ulteriori informazioni.  
  
 Utilizzare il Disassembler MSIL di common language runtime (`Ildasm.exe`) per visualizzare i nomi di spazio dei nomi nel file di output.  
  
|Per impostare /rootnamespace in Visual Studio ambiente di sviluppo integrato.|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Applicazione** .<br />3.  Modificare il valore di **radice Namespace** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e include tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Ildasm.exe (Disassembler IL)](https://msdn.microsoft.com/library/f7dy01k1)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
