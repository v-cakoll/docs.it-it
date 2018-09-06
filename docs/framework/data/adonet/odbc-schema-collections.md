---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877531"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="0ba77-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="0ba77-102">ODBC Schema Collections</span></span>
<span data-ttu-id="0ba77-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="0ba77-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="0ba77-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ba77-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="0ba77-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="0ba77-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0ba77-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="0ba77-106">Tables</span></span>  
  
-   <span data-ttu-id="0ba77-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="0ba77-107">Indexes</span></span>  
  
-   <span data-ttu-id="0ba77-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-108">Columns</span></span>  
  
-   <span data-ttu-id="0ba77-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-109">Procedures</span></span>  
  
-   <span data-ttu-id="0ba77-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0ba77-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0ba77-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0ba77-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="0ba77-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0ba77-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="0ba77-113">Tables and Views</span></span>  
  
|<span data-ttu-id="0ba77-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-114">ColumnName</span></span>|<span data-ttu-id="0ba77-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-116">TABLE_CAT</span></span>|<span data-ttu-id="0ba77-117">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-117">String</span></span>|  
|<span data-ttu-id="0ba77-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-118">TABLE_SCHEM</span></span>|<span data-ttu-id="0ba77-119">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-119">String</span></span>|  
|<span data-ttu-id="0ba77-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-120">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-121">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-121">String</span></span>|  
|<span data-ttu-id="0ba77-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-122">TABLE_TYPE</span></span>|<span data-ttu-id="0ba77-123">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-123">String</span></span>|  
|<span data-ttu-id="0ba77-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-124">REMARKS</span></span>|<span data-ttu-id="0ba77-125">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0ba77-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="0ba77-126">Indexes</span></span>  
  
|<span data-ttu-id="0ba77-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-127">ColumnName</span></span>|<span data-ttu-id="0ba77-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-129">TABLE_CAT</span></span>|<span data-ttu-id="0ba77-130">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-130">String</span></span>|  
|<span data-ttu-id="0ba77-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-131">TABLE_SCHEM</span></span>|<span data-ttu-id="0ba77-132">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-132">String</span></span>|  
|<span data-ttu-id="0ba77-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-133">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-134">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-134">String</span></span>|  
|<span data-ttu-id="0ba77-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0ba77-135">NON_UNIQUE</span></span>|<span data-ttu-id="0ba77-136">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-136">Int16</span></span>|  
|<span data-ttu-id="0ba77-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="0ba77-138">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-138">String</span></span>|  
|<span data-ttu-id="0ba77-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-139">INDEX_NAME</span></span>|<span data-ttu-id="0ba77-140">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-140">String</span></span>|  
|<span data-ttu-id="0ba77-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-141">TYPE</span></span>|<span data-ttu-id="0ba77-142">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-142">Int16</span></span>|  
|<span data-ttu-id="0ba77-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-144">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-144">Int16</span></span>|  
|<span data-ttu-id="0ba77-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-145">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-146">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-146">String</span></span>|  
|<span data-ttu-id="0ba77-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="0ba77-147">ASC_OR_DESC</span></span>|<span data-ttu-id="0ba77-148">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-148">String</span></span>|  
|<span data-ttu-id="0ba77-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="0ba77-149">CARDINATLITY</span></span>|<span data-ttu-id="0ba77-150">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-150">Int32</span></span>|  
|<span data-ttu-id="0ba77-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="0ba77-151">PAGES</span></span>|<span data-ttu-id="0ba77-152">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-152">Int32</span></span>|  
|<span data-ttu-id="0ba77-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-153">FILTER_CONDITION</span></span>|<span data-ttu-id="0ba77-154">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-154">String</span></span>|  
|<span data-ttu-id="0ba77-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0ba77-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0ba77-156">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-156">String</span></span>|  
|<span data-ttu-id="0ba77-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-158">Byte</span><span class="sxs-lookup"><span data-stu-id="0ba77-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0ba77-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-159">Columns</span></span>  
  
|<span data-ttu-id="0ba77-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-160">ColumnName</span></span>|<span data-ttu-id="0ba77-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-162">TABLE_CAT</span></span>|<span data-ttu-id="0ba77-163">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-163">String</span></span>|  
|<span data-ttu-id="0ba77-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-164">TABLE_SCHEM</span></span>|<span data-ttu-id="0ba77-165">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-165">String</span></span>|  
|<span data-ttu-id="0ba77-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-166">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-167">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-167">String</span></span>|  
|<span data-ttu-id="0ba77-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-168">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-169">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-169">String</span></span>|  
|<span data-ttu-id="0ba77-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-170">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-171">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-171">Int16</span></span>|  
|<span data-ttu-id="0ba77-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-172">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-173">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-173">String</span></span>|  
|<span data-ttu-id="0ba77-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0ba77-174">COLUMN_SIZE</span></span>|<span data-ttu-id="0ba77-175">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-175">Int32</span></span>|  
|<span data-ttu-id="0ba77-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="0ba77-177">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-177">Int32</span></span>|  
|<span data-ttu-id="0ba77-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0ba77-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0ba77-179">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-179">Int16</span></span>|  
|<span data-ttu-id="0ba77-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0ba77-181">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-181">Int16</span></span>|  
|<span data-ttu-id="0ba77-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-182">NULLABLE</span></span>|<span data-ttu-id="0ba77-183">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-183">Int16</span></span>|  
|<span data-ttu-id="0ba77-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-184">REMARKS</span></span>|<span data-ttu-id="0ba77-185">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-185">String</span></span>|  
|<span data-ttu-id="0ba77-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0ba77-186">COLUMN_DEF</span></span>|<span data-ttu-id="0ba77-187">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-187">String</span></span>|  
|<span data-ttu-id="0ba77-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-189">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-189">Int16</span></span>|  
|<span data-ttu-id="0ba77-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0ba77-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0ba77-191">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-191">Int16</span></span>|  
|<span data-ttu-id="0ba77-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0ba77-193">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-193">Int32</span></span>|  
|<span data-ttu-id="0ba77-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-195">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-195">Int32</span></span>|  
|<span data-ttu-id="0ba77-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-196">IS_NULLABLE</span></span>|<span data-ttu-id="0ba77-197">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-197">String</span></span>|  
|<span data-ttu-id="0ba77-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0ba77-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0ba77-199">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-199">String</span></span>|  
|<span data-ttu-id="0ba77-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0ba77-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0ba77-201">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-201">String</span></span>|  
|<span data-ttu-id="0ba77-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-203">Byte</span><span class="sxs-lookup"><span data-stu-id="0ba77-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0ba77-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-204">Procedures</span></span>  
  
|<span data-ttu-id="0ba77-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-205">ColumnName</span></span>|<span data-ttu-id="0ba77-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="0ba77-208">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-208">String</span></span>|  
|<span data-ttu-id="0ba77-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0ba77-210">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-210">String</span></span>|  
|<span data-ttu-id="0ba77-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-212">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-212">String</span></span>|  
|<span data-ttu-id="0ba77-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-214">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-214">Int32</span></span>|  
|<span data-ttu-id="0ba77-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-216">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-216">Int32</span></span>|  
|<span data-ttu-id="0ba77-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0ba77-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0ba77-218">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-218">Int32</span></span>|  
|<span data-ttu-id="0ba77-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-219">REMARKS</span></span>|<span data-ttu-id="0ba77-220">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-220">String</span></span>|  
|<span data-ttu-id="0ba77-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0ba77-222">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0ba77-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0ba77-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-224">ColumnName</span></span>|<span data-ttu-id="0ba77-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="0ba77-227">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-227">String</span></span>|  
|<span data-ttu-id="0ba77-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0ba77-229">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-229">String</span></span>|  
|<span data-ttu-id="0ba77-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-231">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-231">String</span></span>|  
|<span data-ttu-id="0ba77-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-232">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-233">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-233">String</span></span>|  
|<span data-ttu-id="0ba77-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-234">COLUMN_TYPE</span></span>|<span data-ttu-id="0ba77-235">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-235">Int16</span></span>|  
|<span data-ttu-id="0ba77-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-236">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-237">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-237">Int16</span></span>|  
|<span data-ttu-id="0ba77-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-238">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-239">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-239">String</span></span>|  
|<span data-ttu-id="0ba77-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0ba77-240">COLUMN_SIZE</span></span>|<span data-ttu-id="0ba77-241">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-241">Int32</span></span>|  
|<span data-ttu-id="0ba77-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="0ba77-243">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-243">Int32</span></span>|  
|<span data-ttu-id="0ba77-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0ba77-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0ba77-245">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-245">Int16</span></span>|  
|<span data-ttu-id="0ba77-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0ba77-247">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-247">Int16</span></span>|  
|<span data-ttu-id="0ba77-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-248">NULLABLE</span></span>|<span data-ttu-id="0ba77-249">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-249">Int16</span></span>|  
|<span data-ttu-id="0ba77-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-250">REMARKS</span></span>|<span data-ttu-id="0ba77-251">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-251">String</span></span>|  
|<span data-ttu-id="0ba77-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0ba77-252">COLUMN_DEF</span></span>|<span data-ttu-id="0ba77-253">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-253">String</span></span>|  
|<span data-ttu-id="0ba77-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-255">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-255">Int16</span></span>|  
|<span data-ttu-id="0ba77-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0ba77-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0ba77-257">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-257">Int16</span></span>|  
|<span data-ttu-id="0ba77-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0ba77-259">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-259">Int32</span></span>|  
|<span data-ttu-id="0ba77-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-261">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-261">Int32</span></span>|  
|<span data-ttu-id="0ba77-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-262">IS_NULLABLE</span></span>|<span data-ttu-id="0ba77-263">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-263">String</span></span>|  
|<span data-ttu-id="0ba77-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0ba77-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0ba77-265">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-265">String</span></span>|  
|<span data-ttu-id="0ba77-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0ba77-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0ba77-267">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-267">String</span></span>|  
|<span data-ttu-id="0ba77-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-269">Byte</span><span class="sxs-lookup"><span data-stu-id="0ba77-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0ba77-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0ba77-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0ba77-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-271">ColumnName</span></span>|<span data-ttu-id="0ba77-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="0ba77-274">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-274">String</span></span>|  
|<span data-ttu-id="0ba77-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0ba77-276">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-276">String</span></span>|  
|<span data-ttu-id="0ba77-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-278">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-278">String</span></span>|  
|<span data-ttu-id="0ba77-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-279">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-280">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-280">String</span></span>|  
|<span data-ttu-id="0ba77-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-281">COLUMN_TYPE</span></span>|<span data-ttu-id="0ba77-282">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-282">Int16</span></span>|  
|<span data-ttu-id="0ba77-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-283">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-284">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-284">Int16</span></span>|  
|<span data-ttu-id="0ba77-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-285">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-286">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-286">String</span></span>|  
|<span data-ttu-id="0ba77-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0ba77-287">COLUMN_SIZE</span></span>|<span data-ttu-id="0ba77-288">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-288">Int32</span></span>|  
|<span data-ttu-id="0ba77-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="0ba77-290">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-290">Int32</span></span>|  
|<span data-ttu-id="0ba77-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0ba77-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0ba77-292">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-292">Int16</span></span>|  
|<span data-ttu-id="0ba77-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0ba77-294">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-294">Int16</span></span>|  
|<span data-ttu-id="0ba77-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-295">NULLABLE</span></span>|<span data-ttu-id="0ba77-296">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-296">Int16</span></span>|  
|<span data-ttu-id="0ba77-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-297">REMARKS</span></span>|<span data-ttu-id="0ba77-298">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-298">String</span></span>|  
|<span data-ttu-id="0ba77-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0ba77-299">COLUMN_DEF</span></span>|<span data-ttu-id="0ba77-300">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-300">String</span></span>|  
|<span data-ttu-id="0ba77-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-302">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-302">Int16</span></span>|  
|<span data-ttu-id="0ba77-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0ba77-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0ba77-304">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-304">Int16</span></span>|  
|<span data-ttu-id="0ba77-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0ba77-306">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-306">Int32</span></span>|  
|<span data-ttu-id="0ba77-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-308">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-308">Int32</span></span>|  
|<span data-ttu-id="0ba77-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-309">IS_NULLABLE</span></span>|<span data-ttu-id="0ba77-310">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-310">String</span></span>|  
|<span data-ttu-id="0ba77-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0ba77-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="0ba77-312">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-312">String</span></span>|  
|<span data-ttu-id="0ba77-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0ba77-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="0ba77-314">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-314">String</span></span>|  
|<span data-ttu-id="0ba77-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-316">Byte</span><span class="sxs-lookup"><span data-stu-id="0ba77-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="0ba77-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="0ba77-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="0ba77-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="0ba77-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0ba77-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="0ba77-319">Tables</span></span>  
  
-   <span data-ttu-id="0ba77-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-320">Columns</span></span>  
  
-   <span data-ttu-id="0ba77-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-321">Procedures</span></span>  
  
-   <span data-ttu-id="0ba77-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0ba77-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0ba77-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0ba77-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="0ba77-324">Views</span></span>  
  
-   <span data-ttu-id="0ba77-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="0ba77-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0ba77-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="0ba77-326">Tables and Views</span></span>  
  
|<span data-ttu-id="0ba77-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-327">ColumnName</span></span>|<span data-ttu-id="0ba77-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-330">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-330">String</span></span>|  
|<span data-ttu-id="0ba77-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-331">TABLE_OWNER</span></span>|<span data-ttu-id="0ba77-332">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-332">String</span></span>|  
|<span data-ttu-id="0ba77-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-333">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-334">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-334">String</span></span>|  
|<span data-ttu-id="0ba77-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-335">TABLE_TYPE</span></span>|<span data-ttu-id="0ba77-336">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-336">String</span></span>|  
|<span data-ttu-id="0ba77-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-337">REMARKS</span></span>|<span data-ttu-id="0ba77-338">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0ba77-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-339">Columns</span></span>  
  
|<span data-ttu-id="0ba77-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-340">ColumnName</span></span>|<span data-ttu-id="0ba77-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-343">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-343">String</span></span>|  
|<span data-ttu-id="0ba77-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-344">TABLE_OWNER</span></span>|<span data-ttu-id="0ba77-345">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-345">String</span></span>|  
|<span data-ttu-id="0ba77-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-346">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-347">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-347">String</span></span>|  
|<span data-ttu-id="0ba77-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-348">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-349">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-349">String</span></span>|  
|<span data-ttu-id="0ba77-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-350">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-351">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-351">Int16</span></span>|  
|<span data-ttu-id="0ba77-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-352">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-353">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-353">String</span></span>|  
|<span data-ttu-id="0ba77-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0ba77-354">PRECISION</span></span>|<span data-ttu-id="0ba77-355">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-355">Int32</span></span>|  
|<span data-ttu-id="0ba77-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-356">LENGTH</span></span>|<span data-ttu-id="0ba77-357">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-357">Int32</span></span>|  
|<span data-ttu-id="0ba77-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="0ba77-358">SCALE</span></span>|<span data-ttu-id="0ba77-359">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-359">Int16</span></span>|  
|<span data-ttu-id="0ba77-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-360">RADIX</span></span>|<span data-ttu-id="0ba77-361">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-361">Int16</span></span>|  
|<span data-ttu-id="0ba77-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-362">NULLABLE</span></span>|<span data-ttu-id="0ba77-363">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-363">Int16</span></span>|  
|<span data-ttu-id="0ba77-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-364">REMARKS</span></span>|<span data-ttu-id="0ba77-365">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-365">String</span></span>|  
|<span data-ttu-id="0ba77-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-367">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0ba77-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-368">Procedures</span></span>  
  
|<span data-ttu-id="0ba77-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-369">ColumnName</span></span>|<span data-ttu-id="0ba77-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-372">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-372">String</span></span>|  
|<span data-ttu-id="0ba77-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0ba77-374">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-374">String</span></span>|  
|<span data-ttu-id="0ba77-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-376">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-376">String</span></span>|  
|<span data-ttu-id="0ba77-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-378">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-378">Int16</span></span>|  
|<span data-ttu-id="0ba77-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-380">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-380">Int16</span></span>|  
|<span data-ttu-id="0ba77-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0ba77-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0ba77-382">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-382">Int16</span></span>|  
|<span data-ttu-id="0ba77-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-383">REMARKS</span></span>|<span data-ttu-id="0ba77-384">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-384">String</span></span>|  
|<span data-ttu-id="0ba77-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0ba77-386">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0ba77-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0ba77-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-388">ColumnName</span></span>|<span data-ttu-id="0ba77-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-391">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-391">String</span></span>|  
|<span data-ttu-id="0ba77-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0ba77-393">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-393">String</span></span>|  
|<span data-ttu-id="0ba77-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-395">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-395">String</span></span>|  
|<span data-ttu-id="0ba77-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-396">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-397">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-397">String</span></span>|  
|<span data-ttu-id="0ba77-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-398">COLUMN_TYPE</span></span>|<span data-ttu-id="0ba77-399">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-399">Int16</span></span>|  
|<span data-ttu-id="0ba77-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-400">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-401">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-401">Int16</span></span>|  
|<span data-ttu-id="0ba77-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-402">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-403">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-403">String</span></span>|  
|<span data-ttu-id="0ba77-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0ba77-404">PRECISION</span></span>|<span data-ttu-id="0ba77-405">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-405">Int32</span></span>|  
|<span data-ttu-id="0ba77-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-406">LENGTH</span></span>|<span data-ttu-id="0ba77-407">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-407">Int32</span></span>|  
|<span data-ttu-id="0ba77-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="0ba77-408">SCALE</span></span>|<span data-ttu-id="0ba77-409">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-409">Int16</span></span>|  
|<span data-ttu-id="0ba77-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-410">RADIX</span></span>|<span data-ttu-id="0ba77-411">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-411">Int16</span></span>|  
|<span data-ttu-id="0ba77-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-412">NULLABLE</span></span>|<span data-ttu-id="0ba77-413">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-413">Int16</span></span>|  
|<span data-ttu-id="0ba77-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-414">REMARKS</span></span>|<span data-ttu-id="0ba77-415">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-415">String</span></span>|  
|<span data-ttu-id="0ba77-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0ba77-416">OVERLOAD</span></span>|<span data-ttu-id="0ba77-417">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-417">Int32</span></span>|  
|<span data-ttu-id="0ba77-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-419">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="0ba77-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="0ba77-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="0ba77-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba77-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="0ba77-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="0ba77-422">Tables</span></span>  
  
-   <span data-ttu-id="0ba77-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="0ba77-423">Indexes</span></span>  
  
-   <span data-ttu-id="0ba77-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-424">Columns</span></span>  
  
-   <span data-ttu-id="0ba77-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-425">Procedures</span></span>  
  
-   <span data-ttu-id="0ba77-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="0ba77-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0ba77-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="0ba77-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="0ba77-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="0ba77-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="0ba77-429">Tables and Views</span></span>  
  
|<span data-ttu-id="0ba77-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-430">ColumnName</span></span>|<span data-ttu-id="0ba77-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-433">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-433">String</span></span>|  
|<span data-ttu-id="0ba77-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-434">TABLE_OWNER</span></span>|<span data-ttu-id="0ba77-435">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-435">String</span></span>|  
|<span data-ttu-id="0ba77-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-436">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-437">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-437">String</span></span>|  
|<span data-ttu-id="0ba77-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-438">TABLE_TYPE</span></span>|<span data-ttu-id="0ba77-439">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-439">String</span></span>|  
|<span data-ttu-id="0ba77-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-440">REMARKS</span></span>|<span data-ttu-id="0ba77-441">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0ba77-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ba77-442">Columns</span></span>  
  
|<span data-ttu-id="0ba77-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-443">ColumnName</span></span>|<span data-ttu-id="0ba77-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-446">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-446">String</span></span>|  
|<span data-ttu-id="0ba77-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-447">TABLE_OWNER</span></span>|<span data-ttu-id="0ba77-448">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-448">String</span></span>|  
|<span data-ttu-id="0ba77-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-449">TABLE_NAME</span></span>|<span data-ttu-id="0ba77-450">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-450">String</span></span>|  
|<span data-ttu-id="0ba77-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-451">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-452">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-452">String</span></span>|  
|<span data-ttu-id="0ba77-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-453">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-454">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-454">Int16</span></span>|  
|<span data-ttu-id="0ba77-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-455">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-456">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-456">String</span></span>|  
|<span data-ttu-id="0ba77-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0ba77-457">PRECISION</span></span>|<span data-ttu-id="0ba77-458">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-458">Int32</span></span>|  
|<span data-ttu-id="0ba77-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-459">LENGTH</span></span>|<span data-ttu-id="0ba77-460">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-460">Int32</span></span>|  
|<span data-ttu-id="0ba77-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="0ba77-461">SCALE</span></span>|<span data-ttu-id="0ba77-462">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-462">Int16</span></span>|  
|<span data-ttu-id="0ba77-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-463">RADIX</span></span>|<span data-ttu-id="0ba77-464">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-464">Int16</span></span>|  
|<span data-ttu-id="0ba77-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-465">NULLABLE</span></span>|<span data-ttu-id="0ba77-466">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-466">Int16</span></span>|  
|<span data-ttu-id="0ba77-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-467">REMARKS</span></span>|<span data-ttu-id="0ba77-468">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-468">String</span></span>|  
|<span data-ttu-id="0ba77-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-470">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0ba77-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="0ba77-471">Procedures</span></span>  
  
|<span data-ttu-id="0ba77-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-472">ColumnName</span></span>|<span data-ttu-id="0ba77-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-475">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-475">String</span></span>|  
|<span data-ttu-id="0ba77-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0ba77-477">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-477">String</span></span>|  
|<span data-ttu-id="0ba77-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-479">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-479">String</span></span>|  
|<span data-ttu-id="0ba77-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-481">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-481">Int16</span></span>|  
|<span data-ttu-id="0ba77-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="0ba77-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="0ba77-483">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-483">Int16</span></span>|  
|<span data-ttu-id="0ba77-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="0ba77-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="0ba77-485">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-485">Int16</span></span>|  
|<span data-ttu-id="0ba77-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-486">REMARKS</span></span>|<span data-ttu-id="0ba77-487">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-487">String</span></span>|  
|<span data-ttu-id="0ba77-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0ba77-489">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0ba77-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0ba77-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0ba77-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-491">ColumnName</span></span>|<span data-ttu-id="0ba77-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="0ba77-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="0ba77-494">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-494">String</span></span>|  
|<span data-ttu-id="0ba77-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba77-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="0ba77-496">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-496">String</span></span>|  
|<span data-ttu-id="0ba77-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-498">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-498">String</span></span>|  
|<span data-ttu-id="0ba77-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-499">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-500">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-500">String</span></span>|  
|<span data-ttu-id="0ba77-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-501">COLUMN_TYPE</span></span>|<span data-ttu-id="0ba77-502">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-502">Int16</span></span>|  
|<span data-ttu-id="0ba77-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-503">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-504">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-504">Int16</span></span>|  
|<span data-ttu-id="0ba77-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-505">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-506">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-506">String</span></span>|  
|<span data-ttu-id="0ba77-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="0ba77-507">PRECISION</span></span>|<span data-ttu-id="0ba77-508">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-508">Int32</span></span>|  
|<span data-ttu-id="0ba77-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-509">LENGTH</span></span>|<span data-ttu-id="0ba77-510">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-510">Int32</span></span>|  
|<span data-ttu-id="0ba77-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="0ba77-511">SCALE</span></span>|<span data-ttu-id="0ba77-512">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-512">Int16</span></span>|  
|<span data-ttu-id="0ba77-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-513">RADIX</span></span>|<span data-ttu-id="0ba77-514">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-514">Int16</span></span>|  
|<span data-ttu-id="0ba77-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-515">NULLABLE</span></span>|<span data-ttu-id="0ba77-516">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-516">Int16</span></span>|  
|<span data-ttu-id="0ba77-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-517">REMARKS</span></span>|<span data-ttu-id="0ba77-518">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-518">String</span></span>|  
|<span data-ttu-id="0ba77-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0ba77-519">OVERLOAD</span></span>|<span data-ttu-id="0ba77-520">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-520">Int32</span></span>|  
|<span data-ttu-id="0ba77-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-522">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0ba77-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0ba77-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0ba77-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="0ba77-524">ColumnName</span></span>|<span data-ttu-id="0ba77-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0ba77-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="0ba77-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="0ba77-527">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-527">String</span></span>|  
|<span data-ttu-id="0ba77-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="0ba77-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="0ba77-529">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-529">String</span></span>|  
|<span data-ttu-id="0ba77-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="0ba77-531">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-531">String</span></span>|  
|<span data-ttu-id="0ba77-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-532">COLUMN_NAME</span></span>|<span data-ttu-id="0ba77-533">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-533">String</span></span>|  
|<span data-ttu-id="0ba77-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-534">COLUMN_TYPE</span></span>|<span data-ttu-id="0ba77-535">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-535">Int16</span></span>|  
|<span data-ttu-id="0ba77-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-536">DATA_TYPE</span></span>|<span data-ttu-id="0ba77-537">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-537">Int16</span></span>|  
|<span data-ttu-id="0ba77-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0ba77-538">TYPE_NAME</span></span>|<span data-ttu-id="0ba77-539">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-539">String</span></span>|  
|<span data-ttu-id="0ba77-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="0ba77-540">COLUMN_SIZE</span></span>|<span data-ttu-id="0ba77-541">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-541">Int32</span></span>|  
|<span data-ttu-id="0ba77-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="0ba77-543">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-543">Int32</span></span>|  
|<span data-ttu-id="0ba77-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="0ba77-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="0ba77-545">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-545">Int16</span></span>|  
|<span data-ttu-id="0ba77-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="0ba77-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="0ba77-547">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-547">Int16</span></span>|  
|<span data-ttu-id="0ba77-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-548">NULLABLE</span></span>|<span data-ttu-id="0ba77-549">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-549">Int16</span></span>|  
|<span data-ttu-id="0ba77-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="0ba77-550">REMARKS</span></span>|<span data-ttu-id="0ba77-551">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-551">String</span></span>|  
|<span data-ttu-id="0ba77-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="0ba77-552">COLUMN_DEF</span></span>|<span data-ttu-id="0ba77-553">String</span><span class="sxs-lookup"><span data-stu-id="0ba77-553">String</span></span>|  
|<span data-ttu-id="0ba77-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ba77-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="0ba77-555">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-555">Int16</span></span>|  
|<span data-ttu-id="0ba77-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="0ba77-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="0ba77-557">Int16</span><span class="sxs-lookup"><span data-stu-id="0ba77-557">Int16</span></span>|  
|<span data-ttu-id="0ba77-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0ba77-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="0ba77-559">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-559">Int32</span></span>|  
|<span data-ttu-id="0ba77-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0ba77-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="0ba77-561">Int32</span><span class="sxs-lookup"><span data-stu-id="0ba77-561">Int32</span></span>|  
|<span data-ttu-id="0ba77-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0ba77-562">IS_NULLABLE</span></span>|<span data-ttu-id="0ba77-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ba77-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ba77-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba77-564">See Also</span></span>  
 [<span data-ttu-id="0ba77-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0ba77-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
