# PW-CRUD-Clientes

<div class="cliente-container">
  <header class="cliente-header">
    <h1>Clientes Registrados</h1>
    <p>Veja a lista de clientes cadastrados no sistema.</p>
  </header>

  <main class="cliente-content">
    <section class="cliente-list">
      <div class="cliente-card" *ngFor="let cliente of clientes">
        <h3>{{ cliente.nome }}</h3>
        <p>Email: {{ cliente.email }}</p>
      </div>
    </section>
  </main>
</div>

import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
  selector: 'app-cliente-page',
  standalone: true,
  imports: [CommonModule],
  templateUrl: './cliente-page.component.html',
  styleUrl: './cliente-page.component.css'
})
export class ClientePageComponent {

  clientes = [
    { id: 1, nome: 'João Silva', email: 'joao@gmail.com' },
    { id: 2, nome: 'Maria Oliveira', email: 'maria@gmail.com' },
    { id: 3, nome: 'Pedro Santos', email: 'pedro@gmail.com' }
  ];

}
