---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a>/main
Specifica la classe o il modulo che contiene la procedura `Sub Main`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>Argomenti  
 `location`  
 Obbligatorio. Nome completo per la classe o modulo che contiene il `Sub Main` procedure da chiamare all'avvio del programma. Può essere nel formato **/main:module** o **/Main**.  
  
## <a name="remarks"></a>Note  
 Utilizzare questa opzione quando si crea un file eseguibile o un programma eseguibile. Se il **/Main** opzione viene omessa, il compilatore cerca una routine condivisa valida `Sub Main` in tutti i moduli e le classi pubbliche.  
  
 Vedere [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) per una descrizione delle varie forme del `Main` stored procedure.  
  
 Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce un valore predefinito `Main` routine che avvia l'applicazione se la classe non ha alcun `Main` stored procedure. Ciò consente di compilare il codice nella riga di comando che è stata creata nell'ambiente di sviluppo.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Per impostare /main in Visual Studio ambiente di sviluppo integrato.  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
     Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Fare clic sulla scheda **Applicazione** .  
  
3.  Verificare che il **Attiva framework applicazione** casella di controllo è deselezionata.  
  
4.  Modificare il valore di **oggetto di avvio** casella.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e `T3.vb`, specificando che il `Sub Main` sarà disponibili nella procedura di `Test2` classe.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [NIB: versione di Visual Basic di Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
