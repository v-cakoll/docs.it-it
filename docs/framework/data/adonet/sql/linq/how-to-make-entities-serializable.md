---
title: 'Procedura: Rendere serializzabili le entità'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: fd687ba5dce16baee063f1d3bb9521c6664988b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743284"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="4ad41-102">Procedura: Rendere serializzabili le entità</span><span class="sxs-lookup"><span data-stu-id="4ad41-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="4ad41-103">Quando si genera il codice, è possibile rendere serializzabili le entità.</span><span class="sxs-lookup"><span data-stu-id="4ad41-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="4ad41-104">Le classi di entità vengono decorate con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> e le colonne con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4ad41-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="4ad41-105">Gli sviluppatori che usano Visual Studio è possono usare Progettazione relazionale oggetti per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="4ad41-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="4ad41-106">Se si usa lo strumento da riga di comando SQLMetal, usare il **/serialization** con il `unidirectional` argomento.</span><span class="sxs-lookup"><span data-stu-id="4ad41-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="4ad41-107">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="4ad41-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ad41-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ad41-108">Example</span></span>  
 <span data-ttu-id="4ad41-109">Le righe di comando SQLMetal seguenti consentono di produrre file con entità serializzabili.</span><span class="sxs-lookup"><span data-stu-id="4ad41-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ad41-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad41-110">See also</span></span>

- [<span data-ttu-id="4ad41-111">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="4ad41-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [<span data-ttu-id="4ad41-112">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="4ad41-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
