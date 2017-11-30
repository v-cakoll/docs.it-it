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
ms.openlocfilehash: 8be88bf4834ca58b1fe708eb1ef7188c583fef0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Compila**.<br />3.  Scegliere **Avanzate**.<br />4.  Modificare il valore di **indirizzo di base DLL:** casella. **Nota:** il **indirizzo di base DLL:** casella è di sola lettura, a meno che la destinazione è una DLL.|  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (strumento Nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23)
