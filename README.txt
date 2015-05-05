--------------------------------------------------------
--  Arquivo criado - Terça-feira-Maio-05-2015   
--------------------------------------------------------
DROP TABLE "ArkCliente" cascade constraints;
DROP TABLE "ArkClienteEndereco" cascade constraints;
DROP TABLE "ArkEndereco" cascade constraints;
DROP TABLE "ArkPedido" cascade constraints;
DROP TABLE "ArkPedidoProduto" cascade constraints;
DROP TABLE "ArkProduto" cascade constraints;
DROP SEQUENCE "ARKCLIENTE_SEQ";
DROP SEQUENCE "ARKENDERECO_SEQ";
DROP SEQUENCE "ARKPEDIDO_SEQ";
DROP SEQUENCE "ARKPRODUTO_SEQ";
--------------------------------------------------------
--  DDL for Sequence ARKCLIENTE_SEQ
--------------------------------------------------------

   CREATE SEQUENCE  "ARKCLIENTE_SEQ"  MINVALUE 1 MAXVALUE 9999999999999999999999999999 INCREMENT BY 1 START WITH 1 NOCACHE  NOORDER  NOCYCLE ;
--------------------------------------------------------
--  DDL for Sequence ARKENDERECO_SEQ
--------------------------------------------------------

   CREATE SEQUENCE  "ARKENDERECO_SEQ"  MINVALUE 1 MAXVALUE 9999999999999999999999999999 INCREMENT BY 1 START WITH 1 NOCACHE  NOORDER  NOCYCLE ;
--------------------------------------------------------
--  DDL for Sequence ARKPEDIDO_SEQ
--------------------------------------------------------

   CREATE SEQUENCE  "ARKPEDIDO_SEQ"  MINVALUE 1 MAXVALUE 9999999999999999999999999999 INCREMENT BY 1 START WITH 1 NOCACHE  NOORDER  NOCYCLE ;
--------------------------------------------------------
--  DDL for Sequence ARKPRODUTO_SEQ
--------------------------------------------------------

   CREATE SEQUENCE  "ARKPRODUTO_SEQ"  MINVALUE 1 MAXVALUE 9999999999999999999999999999 INCREMENT BY 1 START WITH 1 NOCACHE  NOORDER  NOCYCLE ;
--------------------------------------------------------
--  DDL for Table ArkCliente
--------------------------------------------------------

  CREATE TABLE "ArkCliente" 
   (	"id" NUMBER, 
	"cpf" VARCHAR2(14 BYTE), 
	"sexo" VARCHAR2(1 BYTE), 
	"nascimento" DATE, 
	"cnpj" VARCHAR2(18 BYTE), 
	"razaoSocial" VARCHAR2(250 BYTE), 
	"inscEstadual" VARCHAR2(15 BYTE), 
	"nome" VARCHAR2(50 BYTE), 
	"email" VARCHAR2(250 BYTE), 
	"senha" VARCHAR2(25 BYTE), 
	"telefone1" VARCHAR2(15 BYTE), 
	"telefone2" VARCHAR2(15 BYTE), 
	"idEndereco" NUMBER
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Table ArkClienteEndereco
--------------------------------------------------------

  CREATE TABLE "ArkClienteEndereco" 
   (	"idCliente" NUMBER, 
	"idEndereco" NUMBER
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Table ArkEndereco
--------------------------------------------------------

  CREATE TABLE "ArkEndereco" 
   (	"id" NUMBER, 
	"logradouro" VARCHAR2(50 BYTE), 
	"numero" NUMBER, 
	"bairro" VARCHAR2(20 BYTE), 
	"cidade" VARCHAR2(50 BYTE), 
	"uf" VARCHAR2(2 BYTE), 
	"cep" VARCHAR2(10 BYTE), 
	"complemento" VARCHAR2(250 BYTE)
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Table ArkPedido
--------------------------------------------------------

  CREATE TABLE "ArkPedido" 
   (	"id" NUMBER, 
	"valorTotal" NUMBER(*,0), 
	"status" VARCHAR2(20 BYTE), 
	"idCliente" NUMBER
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Table ArkPedidoProduto
--------------------------------------------------------

  CREATE TABLE "ArkPedidoProduto" 
   (	"idPedido" NUMBER, 
	"idProduto" NUMBER, 
	"quantidade" NUMBER
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Table ArkProduto
--------------------------------------------------------

  CREATE TABLE "ArkProduto" 
   (	"id" NUMBER, 
	"nome" VARCHAR2(20 BYTE), 
	"preco" NUMBER(*,0), 
	"descricao" VARCHAR2(250 BYTE), 
	"marca" VARCHAR2(20 BYTE), 
	"status" VARCHAR2(1 BYTE)
   ) SEGMENT CREATION IMMEDIATE 
  PCTFREE 10 PCTUSED 40 INITRANS 1 MAXTRANS 255 NOCOMPRESS LOGGING
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
REM INSERTING into "ArkCliente"
SET DEFINE OFF;
REM INSERTING into "ArkClienteEndereco"
SET DEFINE OFF;
REM INSERTING into "ArkEndereco"
SET DEFINE OFF;
REM INSERTING into "ArkPedido"
SET DEFINE OFF;
REM INSERTING into "ArkPedidoProduto"
SET DEFINE OFF;
REM INSERTING into "ArkProduto"
SET DEFINE OFF;
--------------------------------------------------------
--  DDL for Index ArkProduto_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkProduto_PK" ON "ArkProduto" ("id") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Index ArkClienteEndereco_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkClienteEndereco_PK" ON "ArkClienteEndereco" ("idCliente", "idEndereco") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Index ArkPedido_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkPedido_PK" ON "ArkPedido" ("id") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Index ArkPedidoProduto_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkPedidoProduto_PK" ON "ArkPedidoProduto" ("idPedido", "idProduto") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Index ArkEndereco_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkEndereco_PK" ON "ArkEndereco" ("id") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  DDL for Index ArkClientePJ_PK
--------------------------------------------------------

  CREATE UNIQUE INDEX "ArkClientePJ_PK" ON "ArkCliente" ("id") 
  PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM" ;
--------------------------------------------------------
--  Constraints for Table ArkPedidoProduto
--------------------------------------------------------

  ALTER TABLE "ArkPedidoProduto" ADD CONSTRAINT "ArkPedidoProduto_PK" PRIMARY KEY ("idPedido", "idProduto")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkPedidoProduto" MODIFY ("quantidade" NOT NULL ENABLE);
  ALTER TABLE "ArkPedidoProduto" MODIFY ("idProduto" NOT NULL ENABLE);
  ALTER TABLE "ArkPedidoProduto" MODIFY ("idPedido" NOT NULL ENABLE);
--------------------------------------------------------
--  Constraints for Table ArkProduto
--------------------------------------------------------

  ALTER TABLE "ArkProduto" ADD CONSTRAINT "ArkProduto_PK" PRIMARY KEY ("id")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkProduto" MODIFY ("status" NOT NULL ENABLE);
  ALTER TABLE "ArkProduto" MODIFY ("marca" NOT NULL ENABLE);
  ALTER TABLE "ArkProduto" MODIFY ("preco" NOT NULL ENABLE);
  ALTER TABLE "ArkProduto" MODIFY ("nome" NOT NULL ENABLE);
  ALTER TABLE "ArkProduto" MODIFY ("id" NOT NULL ENABLE);
--------------------------------------------------------
--  Constraints for Table ArkCliente
--------------------------------------------------------

  ALTER TABLE "ArkCliente" ADD CONSTRAINT "ArkClientePJ_PK" PRIMARY KEY ("id")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkCliente" MODIFY ("telefone1" NOT NULL ENABLE);
  ALTER TABLE "ArkCliente" MODIFY ("senha" NOT NULL ENABLE);
  ALTER TABLE "ArkCliente" MODIFY ("email" NOT NULL ENABLE);
  ALTER TABLE "ArkCliente" MODIFY ("nome" NOT NULL ENABLE);
  ALTER TABLE "ArkCliente" MODIFY ("id" NOT NULL ENABLE);
--------------------------------------------------------
--  Constraints for Table ArkEndereco
--------------------------------------------------------

  ALTER TABLE "ArkEndereco" ADD CONSTRAINT "ArkEndereco_PK" PRIMARY KEY ("id")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkEndereco" MODIFY ("cep" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("uf" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("cidade" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("bairro" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("numero" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("logradouro" NOT NULL ENABLE);
  ALTER TABLE "ArkEndereco" MODIFY ("id" NOT NULL ENABLE);
--------------------------------------------------------
--  Constraints for Table ArkPedido
--------------------------------------------------------

  ALTER TABLE "ArkPedido" ADD CONSTRAINT "ArkPedido_PK" PRIMARY KEY ("id")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkPedido" MODIFY ("status" NOT NULL ENABLE);
  ALTER TABLE "ArkPedido" MODIFY ("valorTotal" NOT NULL ENABLE);
  ALTER TABLE "ArkPedido" MODIFY ("id" NOT NULL ENABLE);
  ALTER TABLE "ArkPedido" MODIFY ("idCliente" NOT NULL ENABLE);
--------------------------------------------------------
--  Constraints for Table ArkClienteEndereco
--------------------------------------------------------

  ALTER TABLE "ArkClienteEndereco" ADD CONSTRAINT "ArkClienteEndereco_PK" PRIMARY KEY ("idCliente", "idEndereco")
  USING INDEX PCTFREE 10 INITRANS 2 MAXTRANS 255 
  STORAGE(INITIAL 65536 NEXT 1048576 MINEXTENTS 1 MAXEXTENTS 2147483645
  PCTINCREASE 0 FREELISTS 1 FREELIST GROUPS 1 BUFFER_POOL DEFAULT FLASH_CACHE DEFAULT CELL_FLASH_CACHE DEFAULT)
  TABLESPACE "SYSTEM"  ENABLE;
  ALTER TABLE "ArkClienteEndereco" MODIFY ("idEndereco" NOT NULL ENABLE);
  ALTER TABLE "ArkClienteEndereco" MODIFY ("idCliente" NOT NULL ENABLE);
--------------------------------------------------------
--  Ref Constraints for Table ArkCliente
--------------------------------------------------------

  ALTER TABLE "ArkCliente" ADD CONSTRAINT "ArkClienteEnderecoFK" FOREIGN KEY ("idEndereco")
	  REFERENCES "ArkEndereco" ("id") ENABLE;
--------------------------------------------------------
--  Ref Constraints for Table ArkClienteEndereco
--------------------------------------------------------

  ALTER TABLE "ArkClienteEndereco" ADD CONSTRAINT "ArkClienteFK" FOREIGN KEY ("idCliente")
	  REFERENCES "ArkCliente" ("id") ENABLE;
  ALTER TABLE "ArkClienteEndereco" ADD CONSTRAINT "ArkEnderecoFK" FOREIGN KEY ("idEndereco")
	  REFERENCES "ArkEndereco" ("id") ENABLE;
--------------------------------------------------------
--  Ref Constraints for Table ArkPedido
--------------------------------------------------------

  ALTER TABLE "ArkPedido" ADD CONSTRAINT "ClienteFk" FOREIGN KEY ("idCliente")
	  REFERENCES "ArkCliente" ("id") ENABLE;
--------------------------------------------------------
--  Ref Constraints for Table ArkPedidoProduto
--------------------------------------------------------

  ALTER TABLE "ArkPedidoProduto" ADD CONSTRAINT "ArkPedidoFK" FOREIGN KEY ("idPedido")
	  REFERENCES "ArkPedido" ("id") ENABLE;
  ALTER TABLE "ArkPedidoProduto" ADD CONSTRAINT "ArkProdutoFK" FOREIGN KEY ("idProduto")
	  REFERENCES "ArkProduto" ("id") ENABLE;
