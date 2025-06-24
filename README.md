# PW-CRUD-Clientes

import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-cliente-page',
  standalone: true,
  imports: [CommonModule, FormsModule],
  templateUrl: './cliente-page.component.html',
  styleUrls: ['./cliente-page.component.css']
})
export class ClientePageComponent {
  clientes = [
    { nome: 'João Silva', email: 'joao@gmail.com' },
    { nome: 'Maria Oliveira', email: 'maria@hotmail.com' },
    { nome: 'Carlos Souza', email: 'carlos@yahoo.com' }
  ];

  novoNome = '';
  novoEmail = '';
  editandoIndex: number | null = null;

  adicionarCliente() {
    if (this.novoNome && this.novoEmail) {
      this.clientes.push({ nome: this.novoNome, email: this.novoEmail });
      this.novoNome = '';
      this.novoEmail = '';
    }
  }

  editarCliente(index: number) {
    this.editandoIndex = index;
    this.novoNome = this.clientes[index].nome;
    this.novoEmail = this.clientes[index].email;
  }

  salvarEdicao() {
    if (this.editandoIndex !== null) {
      this.clientes[this.editandoIndex] = { nome: this.novoNome, email: this.novoEmail };
      this.editandoIndex = null;
      this.novoNome = '';
      this.novoEmail = '';
    }
  }

  cancelarEdicao() {
    this.editandoIndex = null;
    this.novoNome = '';
    this.novoEmail = '';
  }

  excluirCliente(index: number) {
    this.clientes.splice(index, 1);
  }
}
