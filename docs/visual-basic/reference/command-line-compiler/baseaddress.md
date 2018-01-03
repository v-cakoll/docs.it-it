---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1ad39acdec92667fbb0848a1c64c567b504dcb67
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="baseaddress"></a>/baseaddress
Specifica un indirizzo di base predefinito durante la creazione di una DLL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`address`|Obbligatorio. Indirizzo di base per la DLL. Questo indirizzo deve essere specificato come numero esadecimale.|  
  
## <a name="remarks"></a>Note  
 L'indirizzo di base predefinito per una DLL è l'impostazione di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 Tenere presente che l'ordine inferiore in questo indirizzo viene arrotondato. Ad esempio, se si specifica 0x11110001, verrà arrotondato a 0x11110000.  
  
 Per completare il processo di firma di una DLL, utilizzare il `–R` opzione dello strumento nome sicuro (Sn.exe).  
  
 Questa opzione viene ignorata se la destinazione non è una DLL.  
  
|Per impostare /baseaddress nell'IDE di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Scegliere **Avanzate**.<br />4.  Modificare il valore di **indirizzo di base DLL:** casella. **Nota:** il **indirizzo di base DLL:** casella è di sola lettura, a meno che la destinazione è una DLL.|  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (strumento nome sicuro)] [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md))
