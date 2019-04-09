---
title: Oggetti DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208814"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="a85f9-102">Oggetti DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="a85f9-102">DbProviderFactories</span></span>
<span data-ttu-id="a85f9-103">Lo spazio dei nomi <xref:System.Data.Common> fornisce classi per la creazione di istanze di <xref:System.Data.Common.DbProviderFactory> per l'uso di origini dati specifiche.</span><span class="sxs-lookup"><span data-stu-id="a85f9-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="a85f9-104">Quando si crea un'istanza di <xref:System.Data.Common.DbProviderFactory> e si passano le informazioni sul provider di dati, `DbProviderFactory` è in grado di determinare l'oggetto connessione corretto, fortemente tipizzato, da restituire in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="a85f9-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="a85f9-105">A partire dalla versione 4 di .NET Framework, i provider di dati come <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>, a differenza dei provider personalizzati, non vengono più elencati nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="a85f9-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a85f9-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a85f9-106">In This Section</span></span>  
 [<span data-ttu-id="a85f9-107">Cenni preliminari sul modello di factory</span><span class="sxs-lookup"><span data-stu-id="a85f9-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="a85f9-108">Viene fornita una panoramica del modello di progettazione e dell'interfaccia di programmazione di factory.</span><span class="sxs-lookup"><span data-stu-id="a85f9-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="a85f9-109">Recupero di un oggetto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="a85f9-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="a85f9-110">Viene illustrato come elencare i provider di dati installati e creare un oggetto <xref:System.Data.Common.DbConnection> da `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="a85f9-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="a85f9-111">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="a85f9-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="a85f9-112">Viene illustrato come creare oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbDataReader> nonché come gestire gli errori di dati tramite <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="a85f9-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="a85f9-113">Modifica di dati con un oggetto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="a85f9-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="a85f9-114">Viene illustrato come usare <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="a85f9-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a85f9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a85f9-115">See also</span></span>

- [<span data-ttu-id="a85f9-116">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a85f9-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="a85f9-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a85f9-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
