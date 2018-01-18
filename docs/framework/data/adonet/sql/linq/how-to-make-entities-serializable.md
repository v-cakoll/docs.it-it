---
title: "Procedura: rendere serializzabili le entità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8f6121b8548c1909f4680419a1fee8f9848ebc1d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="edd03-102">Procedura: rendere serializzabili le entità</span><span class="sxs-lookup"><span data-stu-id="edd03-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="edd03-103">Quando si genera il codice, è possibile rendere serializzabili le entità.</span><span class="sxs-lookup"><span data-stu-id="edd03-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="edd03-104">Le classi di entità vengono decorate con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> e le colonne con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="edd03-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="edd03-105">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="edd03-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="edd03-106">Se si utilizza lo strumento da riga di comando SQLMetal, usare il **/serialization** con il `unidirectional` argomento.</span><span class="sxs-lookup"><span data-stu-id="edd03-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="edd03-107">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="edd03-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="edd03-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="edd03-108">Example</span></span>  
 <span data-ttu-id="edd03-109">Le righe di comando SQLMetal seguenti consentono di produrre file con entità serializzabili.</span><span class="sxs-lookup"><span data-stu-id="edd03-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="edd03-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edd03-110">See Also</span></span>  
 [<span data-ttu-id="edd03-111">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="edd03-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="edd03-112">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="edd03-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
