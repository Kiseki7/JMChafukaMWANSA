<!DOCTYPE html>
<html lang="en">
</head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Phone Book App</title>


    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/css/bootstrap.min.css" rel="stylesheet"
          integrity="sha384-KK94CHFLLe+nY2dmCWGMq91rCGa5gtU4mk92HdvYe+M/SXH301p5ILy+dN9+nJOZ" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/js/bootstrap.bundle.min.js"
            integrity="sha384-ENjdO4Dr2bkBIFxQpeoTz1HIcje39Wm4jDKdf19U8gI4ddQ3GYNS7NTKfAdVQSZe" crossorigin="anonymous">
    </script>
    <div class="container mt-5">
        <form method="POST" action="/addcontact">
            @csrf
    </div>

            <div class="card m-2" >
                <div class="card-header" >
                    <h2>CONTACT DETAILS</h2>
                </div>
                <div class="card-body">
                    <label for="exampleInputEmail1">Email address</label>
                    <input type="email" class="form-control" name="email" placeholder="Enter email">

                    <label for="exampleInputPassword1">Phone Number</label>
                    <input type="text" class="form-control" name="phone" placeholder="Phone">

                    <label for="exampleInputPassword1">address</label>
                    <input type="text" class="form-control" name="address" placeholder="address">

                    <label for="exampleInputPassword1">position</label>
                    <select required type="text" class="form-control" name="position">
                        <option value="">--Select--</option>
                        <option value="Director">Director</option>
                        <option value="HR">HR</option>
                        <option value="Manager">Manager</option>
                    </select>

                    <label for="exampleInputPassword1">department</label>
                    <select required type="text" class="form-control" name="department">
                        <option value="">--Select--</option>
                        <option value="Engineering">Engineering </option>
                        <option value="Social Work">Social Work</option>
                        <option value="Human Capital">Human Capital</option>
                        <option value="Security">Security </option>
                    </select>
                    <div class="card-footer">
                    </div>
                </div>
            </div>

                    <br>
                    <div class="card m-2">
                        <div class="card-header">
                            <h2>PERSONAL DETAILS</h2>
                        </div>
                        <div class="card-body">
                            <label for="exampleInputPassword1">Name</label>
                            <input type="text" class="form-control" name="name" placeholder="Name">

                            <label for="exampleInputPassword1">staff</label>
                            <input type="text" class="form-control" name="staff" placeholder="staff">

                            <label for="exampleInputPassword1">dob</label>
                            <select required type="text" class="form-control" name="dob">
                                <option value="">--Select--</option>
                                <option value="december">december</option>
                                <option value="november">november</option>
                            </select>

                            <label for="exampleInputPassword1">gender</label>
                            <select required type="text" class="form-control" name="gender">
                                <option value="">--Select--</option>
                                <option value="FEMALE">FEMALE</option>
                                <option value="MALE">MALE</option>
                            </select>

                            <label for="exampleInputPassword1">address</label>
                            <input type="text" class="form-control" name="address" placeholder="address">

                            <div class="card-footer">
                            </div>
                        </div>
                        </div>


                            <br>
                            <button type="submit" class="btn btn-primary">Submit</button>
                            <br>
                            <div class="card m-2" >
                                <div class="card-header" >
                                    <h2>USER LIST</h2>
                                </div>
                                <div class="card-body">
                                    <table class="table mt-5">
                                        <thead>
                                        <tr>
                                            <th scope="col">Id</th>
                                            <th scope="col">Name</th>
                                            <th scope="col">Phone</th>
                                            <th scope="col">Email</th>
                                            <th scope="col">staff</th>
                                            <th scope="col">address</th>
                                            <th scope="col">gender</th>
                                            <th scope="col">position</th>
                                            <th scope="col">department</th>
                                            <th scope="col">dob</th>
                                            <th scope="col">Action</th>
                                        </tr>
                                        </thead>
                                        <tbody>
                                        @if (count($contact) > 0)
                                            @foreach ($contact as $cont)
                                                <tr>
                                                    <th>{{ $cont->id }}</th>
                                                    <th>{{ $cont->name }}</th>
                                                    <th>{{ $cont->phone }}</th>
                                                    <th>{{ $cont->email }}</th>
                                                    <th>{{ $cont->staff }}</th>
                                                    <th>{{ $cont->address }}</th>
                                                    <th>{{ $cont->gender }}</th>
                                                    <th>{{ $cont->position }}</th>
                                                    <th>{{ $cont->department }}</th>
                                                    <th>{{ $cont->dob}}</th>
                                                    <th><a href="/edit/{{ $cont->id }}" class="btn btn-primary">Edit</a>
                                                        <a href="/delete/{{ $cont->id }}" class="btn btn-danger">Delete</a>
                                                        <a href="/update/{{ $cont->id }}" class="btn btn-danger">update</a>
                                                    </th>
                                                </tr>
                                            @endforeach
                                        @else
                                            <tr>
                                                <th>No Data</th>
                                            </tr>
                                        @endif
                                        </tbody>
                                    </table>


                                    <div class="card-footer">
                                    </div>
                                </div>
                            </div>


                </div>
            </div>
        </form>
                        </form>
    </div>
<body>
</html>
