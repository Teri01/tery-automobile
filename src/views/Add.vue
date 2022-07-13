<template>
  <div class="contact">
    <header class="masthead">
      <div class="container position-relative px-4 px-lg-5">
        <div class="row gx-4 gx-lg-5 justify-content-center">
          <div class="col-md-10 col-lg-8 col-xl-7">
            <div class="page-heading">
              <h1>Adaugare anunt</h1>
            </div>
          </div>
        </div>
      </div>
    </header>

<form>
  <div class="form-group">
    <label for="Titlul">Titlul</label>
    <input type="text" class="form-control" id="Titlul" placeholder="Titlul">
  </div>
  <div class="form-group">
    <label for="Desscriere">Descriere</label>
    <input type="text" class="form-control" id="Descriere" placeholder="Descriere">
  </div>
   <div class="form-group">
    <label for="Pret">Pret</label>
    <input type="text" class="form-control" id="Pret" placeholder="Pret">
  </div>
  <div class="form-group">
    <label for="Imagini">Imagini</label><br>
    <input type="file" class="form-control-file" id="Imagini">
  </div>
  <br>
  <button type="submit" class="btn btn-primary">Adaugare</button>
</form>

  </div>
</template>

<style scoped>
.masthead {
  background-image: url("../assets/img/contact-bg.jpg");
}
form {
  margin-top: 20px;
  margin-bottom: 20px;
  margin-right: 200px;
  margin-left: 200px;
}
</style>